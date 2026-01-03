
public class CastingDemo {
    /** Main method */
    public static void main(String[] args) {
        // Create and initialize two objects
        Object object1 = new CircleFromSimpleGeometricObject(1);
        Object object2 = new RectangleFromSimpleGeometricObject(1, 1);

        // Display circle and rectangle
        displayObject(object1);
        displayObject(object2);
    }

    /** A method for displaying an object */
    public static void displayObject(Object object) {
        if (object instanceof CircleFromSimpleGeometricObject) {
            System.out.println("The circle area is " +
                    ((CircleFromSimpleGeometricObject)object).getArea());
            System.out.println("The circle diameter is " +
                    ((CircleFromSimpleGeometricObject)object).getDiameter());
        }
        else if (object instanceof
                RectangleFromSimpleGeometricObject) {
            System.out.println("The rectangle area is " +
                    ((RectangleFromSimpleGeometricObject)object).getArea());
        }
    }
}

import javax.swing.*;
        import java.awt.event.*;

public class AnonymousListenerDemo extends JFrame {
    public AnonymousListenerDemo() {
        // Create four buttons
        JButton jbtNew = new JButton("New");
        JButton jbtOpen = new JButton("Open");
        JButton jbtSave = new JButton("Save");
        JButton jbtPrint = new JButton("Print");

        // Create a panel to hold buttons
        JPanel panel = new JPanel();
        panel.add(jbtNew);
        panel.add(jbtOpen);
        panel.add(jbtSave);
        panel.add(jbtPrint);

        add(panel);

        // Create and register anonymous inner class listener
        jbtNew.addActionListener(new ActionListener() {
                                     @Override
                                     public void actionPerformed(ActionEvent e) {
                                         System.out.println("Process New");
                                     }
                                 }
        );

        jbtOpen.addActionListener(new ActionListener() {
                                      @Override
                                      public void actionPerformed(ActionEvent e) {
                                          System.out.println("Process Open");
                                      }
                                  }
        );

        jbtSave.addActionListener(new ActionListener() {
                                      @Override
                                      public void actionPerformed(ActionEvent e) {
                                          System.out.println("Process Save");
                                      }
                                  }
        );

        jbtPrint.addActionListener(new ActionListener() {
                                       @Override
                                       public void actionPerformed(ActionEvent e) {
                                           System.out.println("Process Print");
                                       }
                                   }
        );
    }

    /** Main method */
    public static void main(String[] args) {
        JFrame frame = new AnonymousListenerDemo();
        frame.setTitle("AnonymousListenerDemo");
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.pack();
        frame.setVisible(true);
    }
}

import java.awt.event.*;
        import javax.swing.*;

public class ClockAnimation extends JFrame {
    private StillClock clock = new StillClock();

    public ClockAnimation() {
        add(clock);

        // Create a timer with delay 1000 ms
        Timer timer = new Timer(1000, new TimerListener());
        timer.start();
    }

    private class TimerListener implements ActionListener {
        @Override /** Handle the action event */
        public void actionPerformed(ActionEvent e) {
            // Set new time and repaint the clock to display current time
            clock.setCurrentTime();
            clock.repaint();
        }
    }

    /** Main method */
    public static void main(String[] args) {
        JFrame frame = new ClockAnimation();
        frame.setTitle("ClockAnimation");
        frame.setSize(200, 200);
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}

import javax.swing.*;
        import java.awt.event.*;

public class AnonymousListenerDemo extends JFrame {
    public AnonymousListenerDemo() {
        // Create four buttons
        JButton jbtNew = new JButton("New");
        JButton jbtOpen = new JButton("Open");
        JButton jbtSave = new JButton("Save");
        JButton jbtPrint = new JButton("Print");

        // Create a panel to hold buttons
        JPanel panel = new JPanel();
        panel.add(jbtNew);
        panel.add(jbtOpen);
        panel.add(jbtSave);
        panel.add(jbtPrint);

        add(panel);

        // Create and register anonymous inner class listener
        jbtNew.addActionListener(new ActionListener() {
                                     @Override
                                     public void actionPerformed(ActionEvent e) {
                                         System.out.println("Process New");
                                     }
                                 }
        );

        jbtOpen.addActionListener(new ActionListener() {
                                      @Override
                                      public void actionPerformed(ActionEvent e) {
                                          System.out.println("Process Open");
                                      }
                                  }
        );

        jbtSave.addActionListener(new ActionListener() {
                                      @Override
                                      public void actionPerformed(ActionEvent e) {
                                          System.out.println("Process Save");
                                      }
                                  }
        );

        jbtPrint.addActionListener(new ActionListener() {
                                       @Override
                                       public void actionPerformed(ActionEvent e) {
                                           System.out.println("Process Print");
                                       }
                                   }
        );
    }

    /** Main method */
    public static void main(String[] args) {
        JFrame frame = new AnonymousListenerDemo();
        frame.setTitle("AnonymousListenerDemo");
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.pack();
        frame.setVisible(true);
    }
}

import java.awt.event.*;
        import javax.swing.*;

public class ClockAnimation extends JFrame {
    private StillClock clock = new StillClock();

    public ClockAnimation() {
        add(clock);

        // Create a timer with delay 1000 ms
        Timer timer = new Timer(1000, new TimerListener());
        timer.start();
    }

    private class TimerListener implements ActionListener {
        @Override /** Handle the action event */
        public void actionPerformed(ActionEvent e) {
            // Set new time and repaint the clock to display current time
            clock.setCurrentTime();
            clock.repaint();
        }
    }

    /** Main method */
    public static void main(String[] args) {
        JFrame frame = new ClockAnimation();
        frame.setTitle("ClockAnimation");
        frame.setSize(200, 200);
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}

import javax.swing.*;
        import java.awt.*;
        import java.awt.event.*;

public class ControlCircle extends JFrame {
    private JButton jbtEnlarge = new JButton("Enlarge");
    private JButton jbtShrink = new JButton("Shrink");
    private CirclePanel canvas = new CirclePanel();

    public ControlCircle() {
        JPanel panel = new JPanel(); // Use the panel to group buttons
        panel.add(jbtEnlarge);
        panel.add(jbtShrink);

        this.add(canvas, BorderLayout.CENTER); // Add canvas to center
        this.add(panel, BorderLayout.SOUTH); // Add buttons to the frame

        jbtEnlarge.addActionListener(new EnlargeListener());
    }

    /** Main method */
    public static void main(String[] args) {
        JFrame frame = new ControlCircle();
        frame.setTitle("ControlCircle");
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(200, 200);
        frame.setVisible(true);
    }

    class EnlargeListener implements ActionListener { // Inner class
        @Override
        public void actionPerformed(ActionEvent e) {
            canvas.enlarge();
        }
    }

    class CirclePanel extends JPanel { // Inner class
        private int radius = 5; // Default circle radius

        /** Enlarge the circle */
        public void enlarge() {
            radius++;
            repaint();
        }

        @Override
        protected void paintComponent(Graphics g) {
            super.paintComponent(g);
            g.drawOval(getWidth() / 2 - radius, getHeight() / 2 - radius,
                    2 * radius, 2 * radius);
        }
    }
}

import javax.swing.*;
        import java.awt.*;

public class ControlCircleWithoutEventHandling extends JFrame {
    private JButton jbtEnlarge = new JButton("Enlarge");
    private JButton jbtShrink = new JButton("Shrink");
    private CirclePanel canvas = new CirclePanel();

    public ControlCircleWithoutEventHandling() {
        JPanel panel = new JPanel(); // Use the panel to group buttons
        panel.add(jbtEnlarge);
        panel.add(jbtShrink);

        this.add(canvas, BorderLayout.CENTER); // Add canvas to center
        this.add(panel, BorderLayout.SOUTH); // Add buttons to the frame
    }

    /** Main method */
    public static void main(String[] args) {
        JFrame frame = new ControlCircleWithoutEventHandling();
        frame.setTitle("ControlCircleWithoutEventHandling");
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(200, 200);
        frame.setVisible(true);
    }
}

class CirclePanel extends JPanel {
    private int radius = 5; // Default circle radius

    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        g.drawOval(getWidth() / 2 - radius, getHeight() / 2 - radius,
                2 * radius, 2 * radius);
    }
}

import javax.swing.*;
        import java.awt.event.*;

public class DetectSourceDemo extends JFrame {
    // Create four buttons
    private JButton jbtNew = new JButton("New");
    private JButton jbtOpen = new JButton("Open");
    private JButton jbtSave = new JButton("Save");
    private JButton jbtPrint = new JButton("Print");

    public DetectSourceDemo() {
        // Create a panel to hold buttons
        JPanel panel = new JPanel();
        panel.add(jbtNew);
        panel.add(jbtOpen);
        panel.add(jbtSave);
        panel.add(jbtPrint);

        add(panel);

        // Create a listener
        ButtonListener listener = new ButtonListener();

        // Register listener with buttons
        jbtNew.addActionListener(listener);
        jbtOpen.addActionListener(listener);
        jbtSave.addActionListener(listener);
        jbtPrint.addActionListener(listener);
    }

    class ButtonListener implements ActionListener {
        @Override
        public void actionPerformed(ActionEvent e) {
            if (e.getSource() == jbtNew)
                System.out.println("Process New");
            else if (e.getSource() == jbtOpen)
                System.out.println("Process Open");
            else if (e.getSource() == jbtSave)
                System.out.println("Process Save");
            else if (e.getSource() == jbtPrint)
                System.out.println("Process Print");
        }
    }

    /** Main method */
    public static void main(String[] args) {
        JFrame frame = new DetectSourceDemo();
        frame.setTitle("DetectSourceDemo");
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.pack();
        frame.setVisible(true);
    }
}

import javax.swing.*;
        import java.awt.event.*;

public class FrameAsListenerDemo extends JFrame
        implements ActionListener {
    // Create four buttons
    private JButton jbtNew = new JButton("New");
    private JButton jbtOpen = new JButton("Open");
    private JButton jbtSave = new JButton("Save");
    private JButton jbtPrint = new JButton("Print");

    public FrameAsListenerDemo() {
        // Create a panel to hold buttons
        JPanel panel = new JPanel();
        panel.add(jbtNew);
        panel.add(jbtOpen);
        panel.add(jbtSave);
        panel.add(jbtPrint);

        add(panel);

        // Register listener with buttons
        jbtNew.addActionListener(this);
        jbtOpen.addActionListener(this);
        jbtSave.addActionListener(this);
        jbtPrint.addActionListener(this);
    }

    @Override /** Implement actionPerformed */
    public void actionPerformed(ActionEvent e) {
        if (e.getSource() == jbtNew)
            System.out.println("Process New");
        else if (e.getSource() == jbtOpen)
            System.out.println("Process Open");
        else if (e.getSource() == jbtSave)
            System.out.println("Process Save");
        else if (e.getSource() == jbtPrint)
            System.out.println("Process Print");
    }

    /** Main method */
    public static void main(String[] args) {
        JFrame frame = new FrameAsListenerDemo();
        frame.setTitle("FrameAsListenerDemo");
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.pack();
        frame.setVisible(true);
    }
}

import javax.swing.*;
        import java.awt.event.*;

public class HandleEvent extends JFrame {
    public HandleEvent() {
        // Create two buttons
        JButton jbtOK = new JButton("OK");
        JButton jbtCancel = new JButton("Cancel");

        // Create a panel to hold buttons
        JPanel panel = new JPanel();
        panel.add(jbtOK);
        panel.add(jbtCancel);

        add(panel); // Add panel to the frame

        // Register listeners
        OKListenerClass listener1 = new OKListenerClass();
        CancelListenerClass listener2 = new CancelListenerClass();
        jbtOK.addActionListener(listener1);
        jbtCancel.addActionListener(listener2);
    }

    public static void main(String[] args) {
        JFrame frame = new HandleEvent();
        frame.setTitle("Handle Event");
        frame.setSize(200, 150);
        frame.setLocation(200, 100);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}

class OKListenerClass implements ActionListener {
    @Override
    public void actionPerformed(ActionEvent e) {
        System.out.println("OK button clicked");
    }
}

class CancelListenerClass implements ActionListener {
    @Override
    public void actionPerformed(ActionEvent e) {
        System.out.println("Cancel button clicked");
    }
}
import java.awt.*;
        import java.awt.event.*;
        import javax.swing.*;

public class KeyEventDemo extends JFrame {
    private KeyboardPanel keyboardPanel = new KeyboardPanel();

    /** Initialize UI */
    public KeyEventDemo() {
        // Add the keyboard panel to accept and display user input
        add(keyboardPanel);

        // Set focus
        keyboardPanel.setFocusable(true);
    }

    /** Main method */
    public static void main(String[] args) {
        KeyEventDemo frame = new KeyEventDemo();
        frame.setTitle("KeyEventDemo");
        frame.setSize(300, 300);
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }

    // Inner class: KeyboardPanel for receiving key input
    static class KeyboardPanel extends JPanel {
        private int x = 100;
        private int y = 100;
        private char keyChar = 'A'; // Default key

        public KeyboardPanel() {
            addKeyListener(new KeyAdapter() {
                @Override
                public void keyPressed(KeyEvent e) {
                    switch (e.getKeyCode()) {
                        case KeyEvent.VK_DOWN: y += 10; break;
                        case KeyEvent.VK_UP: y -= 10; break;
                        case KeyEvent.VK_LEFT: x -= 10; break;
                        case KeyEvent.VK_RIGHT: x += 10; break;
                        default: keyChar = e.getKeyChar();
                    }

                    repaint();
                }
            });
        }

        @Override
        protected void paintComponent(Graphics g) {
            super.paintComponent(g);

            g.setFont(new Font("TimesRoman", Font.PLAIN, 24));
            g.drawString(String.valueOf(keyChar), x, y);
        }
    }
}
import java.awt.*;
        import java.awt.event.*;
        import javax.swing.*;
        import javax.swing.border.TitledBorder;

public class LoanCalculator extends JFrame {
    // Create text fields for interest rate, years
    // loan amount, monthly payment, and total payment
    private JTextField jtfAnnualInterestRate = new JTextField();
    private JTextField jtfNumberOfYears = new JTextField();
    private JTextField jtfLoanAmount = new JTextField();
    private JTextField jtfMonthlyPayment = new JTextField();
    private JTextField jtfTotalPayment = new JTextField();

    // Create a Compute Payment button
    private JButton jbtComputeLoan = new JButton("Compute Payment");

    public LoanCalculator() {
        // Panel p1 to hold labels and text fields
        JPanel p1 = new JPanel(new GridLayout(5, 2));
        p1.add(new JLabel("Annual Interest Rate"));
        p1.add(jtfAnnualInterestRate);
        p1.add(new JLabel("Number of Years"));
        p1.add(jtfNumberOfYears);
        p1.add(new JLabel("Loan Amount"));
        p1.add(jtfLoanAmount);
        p1.add(new JLabel("Monthly Payment"));
        p1.add(jtfMonthlyPayment);
        p1.add(new JLabel("Total Payment"));
        p1.add(jtfTotalPayment);
        p1.setBorder(new
                TitledBorder("Enter loan amount, interest rate, and years"));

        // Panel p2 to hold the button
        JPanel p2 = new JPanel(new FlowLayout(FlowLayout.RIGHT));
        p2.add(jbtComputeLoan);

        // Add the panels to the frame
        add(p1, BorderLayout.CENTER);
        add(p2, BorderLayout.SOUTH);

        // Register listener
        jbtComputeLoan.addActionListener(new ButtonListener());
    }

    /** Handle the Compute Payment button */
    private class ButtonListener implements ActionListener {
        @Override
        public void actionPerformed(ActionEvent e) {
            // Get values from text fields
            double interest =
                    Double.parseDouble(jtfAnnualInterestRate.getText());
            int year = Integer.parseInt(jtfNumberOfYears.getText());
            double loanAmount =
                    Double.parseDouble(jtfLoanAmount.getText());

            // Create a loan object
            Loan loan = new Loan(interest, year, loanAmount);

            // Display monthly payment and total payment
            jtfMonthlyPayment.setText(String.format("%.2f",
                    loan.getMonthlyPayment()));
            jtfTotalPayment.setText(String.format("%.2f",
                    loan.getTotalPayment()));
        }
    }

    public static void main(String[] args) {
        LoanCalculator frame = new LoanCalculator();
        frame.pack();
        frame.setTitle("LoanCalculator");
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}
import java.awt.*;
        import java.awt.event.*;
        import javax.swing.*;

public class MoveMessageDemo extends JFrame {
    public MoveMessageDemo() {
        // Create a MovableMessagePanel instance for moving a message
        MovableMessagePanel p = new MovableMessagePanel
                ("Welcome to Java");

        // Place the message panel in the frame
        add(p);
    }

    /** Main method */
    public static void main(String[] args) {
        MoveMessageDemo frame = new MoveMessageDemo();
        frame.setTitle("MoveMessageDemo");
        frame.setSize(200, 100);
        frame.setLocationRelativeTo(null); // Center the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }

    // Inner class: MovableMessagePanel draws a message
    static class MovableMessagePanel extends JPanel {
        private String message = "Welcome to Java";
        private int x = 20;
        private int y = 20;

        /** Construct a panel to draw string s */
        public MovableMessagePanel(String s) {
            message = s;
            addMouseMotionListener(new MouseMotionListener() {
                @Override /** Handle mouse-dragged event */
                public void mouseDragged(MouseEvent e) {
                    // Get the new location and repaint the screen
                    x = e.getX();
                    y = e.getY();
                    repaint();
                }

                @Override /** Handle mouse-moved event */
                public void mouseMoved(MouseEvent e) {
                }
            });
        }

        @Override
        protected void paintComponent(Graphics g) {
            super.paintComponent(g);
            g.drawString(message, x, y);
        }
    }
}
// ShowInnerClass.java: Demonstrate using inner classes
public class ShowInnerClass {
    private int data;

    /** A method in the outer class */
    public void m() {
        // Do something
        InnerClass instance = new InnerClass();
    }

    // An inner class
    class InnerClass {
        /** A method in the inner class */
        public void mi() {
            // Directly reference data and method defined in its outer class
            data++;
            m();
        }
    }
}
public class Circle extends GeometricObject {
    private double radius;

    public Circle() {
    }

    public Circle(double radius) {
        this.radius = radius;
    }

    /** Return radius */
    public double getRadius() {
        return radius;
    }

    /** Set a new radius */
    public void setRadius(double radius) {
        this.radius = radius;
    }

    @Override /** Return area */
    public double getArea() {
        return radius * radius * Math.PI;
    }

    /** Return diameter */
    public double getDiameter() {
        return 2 * radius;
    }

    @Override /** Return perimeter */
    public double getPerimeter() {
        return 2 * radius * Math.PI;
    }

    /* Print the circle info */
    public void printCircle() {
        System.out.println("The circle is created " + getDateCreated() +
                " and the radius is " + radius);
    }
}
public class ComparableRectangle extends Rectangle
        implements Comparable<ComparableRectangle> {
    /** Construct a ComparableRectangle with specified properties */
    public ComparableRectangle(double width, double height) {
        super(width, height);
    }

    @Override // Implement the compareTo method defined in Comparable
    public int compareTo(ComparableRectangle o) {
        if (getArea() > o.getArea())
            return 1;
        else if (getArea() < o.getArea())
            return -1;
        else
            return 0;
    }

    @Override // Implement the toString method in GeometricObject
    public String toString() {
        return "Width: " + getWidth() + " Height: " + getHeight() +
                " Area: " + getArea();
    }
}
public interface Edible {
    /** Describe how to eat */
    public abstract String howToEat();
}
public abstract class GeometricObject {
    private String color = "white";
    private boolean filled;
    private java.util.Date dateCreated;

    /** Construct a default geometric object */
    protected GeometricObject() {
        dateCreated = new java.util.Date();
    }

    /** Construct a geometric object with color and filled value */
    protected GeometricObject(String color, boolean filled) {
        dateCreated = new java.util.Date();
        this.color = color;
        this.filled = filled;
    }

    /** Return color */
    public String getColor() {
        return color;
    }

    /** Set a new color */
    public void setColor(String color) {
        this.color = color;
    }

    /** Return filled. Since filled is boolean,
     *  the get method is named isFilled */
    public boolean isFilled() {
        return filled;
    }

    /** Set a new filled */
    public void setFilled(boolean filled) {
        this.filled = filled;
    }

    /** Get dateCreated */
    public java.util.Date getDateCreated() {
        return dateCreated;
    }

    @Override
    public String toString() {
        return "created on " + dateCreated + "\ncolor: " + color +
                " and filled: " + filled;
    }

    /** Abstract method getArea */
    public abstract double getArea();

    /** Abstract method getPerimeter */
    public abstract double getPerimeter();
}
import javax.swing.*;
        import java.awt.event.*;

public class HandleEvent extends JFrame {
    public HandleEvent() {
        // Create two buttons
        JButton jbtOK = new JButton("OK");
        JButton jbtCancel = new JButton("Cancel");

        // Create a panel to hold buttons
        JPanel panel = new JPanel();
        panel.add(jbtOK);
        panel.add(jbtCancel);

        add(panel); // Add panel to the frame

        // Register listeners
        OKListenerClass listener1 = new OKListenerClass();
        CancelListenerClass listener2 = new CancelListenerClass();
        jbtOK.addActionListener(listener1);
        jbtCancel.addActionListener(listener2);
    }

    public static void main(String[] args) {
        JFrame frame = new HandleEvent();
        frame.setTitle("Handle Event");
        frame.setSize(200, 150);
        frame.setLocation(200, 100);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}

class OKListenerClass implements ActionListener {
    @Override
    public void actionPerformed(ActionEvent e) {
        System.out.println("OK button clicked");
    }
}

class CancelListenerClass implements ActionListener {
    @Override
    public void actionPerformed(ActionEvent e) {
        System.out.println("Cancel button clicked");
    }
}
public class House implements Cloneable, Comparable<House> {
    private int id;
    private double area;
    private java.util.Date whenBuilt;

    public House(int id, double area) {
        this.id = id;
        this.area = area;
        whenBuilt = new java.util.Date();
    }

    public int getId() {
        return id;
    }

    public double getArea() {
        return area;
    }

    public java.util.Date getWhenBuilt() {
        return whenBuilt;
    }

    @Override /** Override the protected clone method defined in
     the Object class, and strengthen its accessibility */
    public Object clone() {
        try {
            return super.clone();
        }
        catch (CloneNotSupportedException ex) {
            return null;
        }
    }

    @Override // Implement the compareTo method defined in Comparable
    public int compareTo(House o) {
        if (area > o.area)
            return 1;
        else if (area < o.area)
            return -1;
        else
            return 0;
    }
}
import java.util.ArrayList;
import java.math.*;

public class LargestNumbers {
    public static void main(String[] args) {
        ArrayList<Number> list = new ArrayList<Number>();
        list.add(45); // Add an integer
        list.add(3445.53); // Add a double
        // Add a BigInteger
        list.add(new BigInteger("3432323234344343101"));
        // Add a BigDecimal
        list.add(new BigDecimal("2.0909090989091343433344343"));

        System.out.println("The largest number is " +
                getLargestNumber(list));
    }

    public static Number getLargestNumber(ArrayList<Number> list) {
        if (list == null || list.size() == 0)
            return null;

        Number number = list.get(0);
        for (int i = 1; i < list.size(); i++)
            if (number.doubleValue() < list.get(i).doubleValue())
                number = list.get(i);

        return number;
    }
}
public class Rational extends Number implements Comparable<Rational> {
    // Data fields for numerator and denominator
    private long numerator = 0;
    private long denominator = 1;

    /** Construct a rational with default properties */
    public Rational() {
        this(0, 1);
    }

    /** Construct a rational with specified numerator and denominator */
    public Rational(long numerator, long denominator) {
        long gcd = gcd(numerator, denominator);
        this.numerator = ((denominator > 0) ? 1 : -1) * numerator / gcd;
        this.denominator = Math.abs(denominator) / gcd;
    }

    /** Find GCD of two numbers */
    private static long gcd(long n, long d) {
        long n1 = Math.abs(n);
        long n2 = Math.abs(d);
        int gcd = 1;

        for (int k = 1; k <= n1 && k <= n2; k++) {
            if (n1 % k == 0 && n2 % k == 0)
                gcd = k;
        }

        return gcd;
    }

    /** Return numerator */
    public long getNumerator() {
        return numerator;
    }

    /** Return denominator */
    public long getDenominator() {
        return denominator;
    }

    /** Add a rational number to this rational */
    public Rational add(Rational secondRational) {
        long n = numerator * secondRational.getDenominator() +
                denominator * secondRational.getNumerator();
        long d = denominator * secondRational.getDenominator();
        return new Rational(n, d);
    }

    /** Subtract a rational number from this rational */
    public Rational subtract(Rational secondRational) {
        long n = numerator * secondRational.getDenominator()
                - denominator * secondRational.getNumerator();
        long d = denominator * secondRational.getDenominator();
        return new Rational(n, d);
    }

    /** Multiply a rational number to this rational */
    public Rational multiply(Rational secondRational) {
        long n = numerator * secondRational.getNumerator();
        long d = denominator * secondRational.getDenominator();
        return new Rational(n, d);
    }

    /** Divide a rational number from this rational */
    public Rational divide(Rational secondRational) {
        long n = numerator * secondRational.getDenominator();
        long d = denominator * secondRational.numerator;
        return new Rational(n, d);
    }

    @Override
    public String toString() {
        if (denominator == 1)
            return numerator + "";
        else
            return numerator + "/" + denominator;
    }

    @Override // Override the equals method in the Object class
    public boolean equals(Object other) {
        if ((this.subtract((Rational)(other))).getNumerator() == 0)
            return true;
        else
            return false;
    }

    @Override // Implement the abstract intValue method in Number
    public int intValue() {
        return (int)doubleValue();
    }

    @Override // Implement the abstract floatValue method in Number
    public float floatValue() {
        return (float)doubleValue();
    }

    @Override // Implement the doubleValue method in Number
    public double doubleValue() {
        return numerator * 1.0 / denominator;
    }

    @Override // Implement the abstract longValue method in Number
    public long longValue() {
        return (long)doubleValue();
    }

    @Override // Implement the compareTo method in Comparable
    public int compareTo(Rational o) {
        if (this.subtract(o).getNumerator() > 0)
            return 1;
        else if (this.subtract(o).getNumerator() < 0)
            return -1;
        else
            return 0;
    }
}
public class Rectangle extends GeometricObject {
    private double width;
    private double height;

    public Rectangle() {
    }

    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }

    /** Return width */
    public double getWidth() {
        return width;
    }

    /** Set a new width */
    public void setWidth(double width) {
        this.width = width;
    }

    /** Return height */
    public double getHeight() {
        return height;
    }

    /** Set a new height */
    public void setHeight(double height) {
        this.height = height;
    }

    @Override /** Return area */
    public double getArea() {
        return width * height;
    }

    @Override /** Return perimeter */
    public double getPerimeter() {
        return 2 * (width + height);
    }
}
import java.math.*;

public class SortComparableObjects {
    public static void main(String[] args) {
        String[] cities = {"Savannah", "Boston", "Atlanta", "Tampa"};
        java.util.Arrays.sort(cities);
        for (String city: cities)
            System.out.print(city + " ");
        System.out.println();

        BigInteger[] hugeNumbers = {new BigInteger("2323231092923992"),
                new BigInteger("432232323239292"),
                new BigInteger("54623239292")};
        java.util.Arrays.sort(hugeNumbers);
        for (BigInteger number: hugeNumbers)
            System.out.print(number + " ");
    }
}
public class SortRectangles {
    public static void main(String[] args) {
        ComparableRectangle[] rectangles = {
                new ComparableRectangle(3.4, 5.4),
                new ComparableRectangle(13.24, 55.4),
                new ComparableRectangle(7.4, 35.4),
                new ComparableRectangle(1.4, 25.4)};
        java.util.Arrays.sort(rectangles);
        for (Rectangle rectangle: rectangles) {
            System.out.print(rectangle + " ");
            System.out.println();
        }
    }
}
import java.util.*;

public class TestCalendar {
    public static void main(String[] args) {
        // Construct a Gregorian calendar for the current date and time
        Calendar calendar = new GregorianCalendar();
        System.out.println("Current time is " + new Date());
        System.out.println("YEAR: " + calendar.get(Calendar.YEAR));
        System.out.println("MONTH: " + calendar.get(Calendar.MONTH));
        System.out.println("DATE: " + calendar.get(Calendar.DATE));
        System.out.println("HOUR: " + calendar.get(Calendar.HOUR));
        System.out.println("HOUR_OF_DAY: " +
                calendar.get(Calendar.HOUR_OF_DAY));
        System.out.println("MINUTE: " + calendar.get(Calendar.MINUTE));
        System.out.println("SECOND: " + calendar.get(Calendar.SECOND));
        System.out.println("DAY_OF_WEEK: " +
                calendar.get(Calendar.DAY_OF_WEEK));
        System.out.println("DAY_OF_MONTH: " +
                calendar.get(Calendar.DAY_OF_MONTH));
        System.out.println("DAY_OF_YEAR: " +
                calendar.get(Calendar.DAY_OF_YEAR));
        System.out.println("WEEK_OF_MONTH: " +
                calendar.get(Calendar.WEEK_OF_MONTH));
        System.out.println("WEEK_OF_YEAR: " +
                calendar.get(Calendar.WEEK_OF_YEAR));
        System.out.println("AM_PM: " + calendar.get(Calendar.AM_PM));

        // Construct a calendar for September 11, 2001
        Calendar calendar1 = new GregorianCalendar(2001, 8, 11);
        String[] dayNameOfWeek = {"Sunday", "Monday", "Tuesday", "Wednesday",
                "Thursday", "Friday", "Saturday"};
        System.out.println("September 11, 2001 is a " +
                dayNameOfWeek[calendar1.get(Calendar.DAY_OF_WEEK) - 1]);
    }
}
public class TestEdible {
    public static void main(String[] args) {
        Object[] objects = {new Tiger(), new Chicken(), new Apple()};
        for (int i = 0; i < objects.length; i++) {
            if (objects[i] instanceof Edible)
                System.out.println(((Edible)objects[i]).howToEat());

            if (objects[i] instanceof Animal) {
                System.out.println(((Animal)objects[i]).sound());
            }
        }
    }
}

abstract class Animal {
    /** Return animal sound */
    public abstract String sound();
}

class Chicken extends Animal implements Edible {
    @Override
    public String howToEat() {
        return "Chicken: Fry it";
    }

    @Override
    public String sound() {
        return "Chicken: cock-a-doodle-doo";
    }
}

class Tiger extends Animal {
    @Override
    public String sound() {
        return "Tiger: RROOAARR";
    }
}

abstract class Fruit implements Edible {
    // Data fields, constructors, and methods omitted here
}

class Apple extends Fruit {
    @Override
    public String howToEat() {
        return "Apple: Make apple cider";
    }
}

class Orange extends Fruit {
    @Override
    public String howToEat() {
        return "Orange: Make orange juice";
    }
}
public class TestGeometricObject {
    /** Main method */
    public static void main(String[] args) {
        // Declare and initialize two geometric objects
        GeometricObject geoObject1 = new Circle(5);
        GeometricObject geoObject2 = new Rectangle(5, 3);

        System.out.println("The two objects have the same area? " +
                equalArea(geoObject1, geoObject2));

        // Display circle
        displayGeometricObject(geoObject1);

        // Display rectangle
        displayGeometricObject(geoObject2);
    }

    /** A method for comparing the areas of two geometric objects */
    public static boolean equalArea(GeometricObject object1,
                                    GeometricObject object2) {
        return object1.getArea() == object2.getArea();
    }

    /** A method for displaying a geometric object */
    public static void displayGeometricObject(GeometricObject object) {
        System.out.println();
        System.out.println("The area is " + object.getArea());
        System.out.println("The perimeter is " + object.getPerimeter());
    }
}
public class TestRationalClass {
    /** Main method */
    public static void main(String[] args) {
        // Create and initialize two rational numbers r1 and r2.
        Rational r1 = new Rational(4, 2);
        Rational r2 = new Rational(2, 3);

        // Display results
        System.out.println(r1 + " + " + r2 + " = " + r1.add(r2));
        System.out.println(r1 + " - " + r2 + " = " + r1.subtract(r2));
        System.out.println(r1 + " * " + r2 + " = " + r1.multiply(r2));
        System.out.println(r1 + " / " + r2 + " = " + r1.divide(r2));
        System.out.println(r2 + " is " + r2.doubleValue());
    }
}
public class CircleWithException {
    /** The radius of the circle */
    private double radius;

    /** The number of the objects created */
    private static int numberOfObjects = 0;

    /** Construct a circle with radius 1 */
    public CircleWithException() {
        this(1.0);
    }

    /** Construct a circle with a specified radius */
    public CircleWithException(double newRadius) {
        setRadius(newRadius);
        numberOfObjects++;
    }

    /** Return radius */
    public double getRadius() {
        return radius;
    }

    /** Set a new radius */
    public void setRadius(double newRadius)
            throws IllegalArgumentException {
        if (newRadius >= 0)
            radius =  newRadius;
        else
            throw new IllegalArgumentException(
                    "Radius cannot be negative");
    }

    /** Return numberOfObjects */
    public static int getNumberOfObjects() {
        return numberOfObjects;
    }

    /** Return the area of this circle */
    public double findArea() {
        return radius * radius * 3.14159;
    }
}
public class CircleWithRadiusException {
    /** The radius of the circle */
    private double radius;

    /** The number of the objects created */
    private static int numberOfObjects = 0;

    /** Construct a circle with radius 1 */
    public CircleWithRadiusException() {
        this(1.0);
    }

    /** Construct a circle with a specified radius */
    public CircleWithRadiusException(double newRadius) {
        try {
            setRadius(newRadius);
            numberOfObjects++;
        }
        catch (InvalidRadiusException ex) {
            ex.printStackTrace();
        }
    }

    /** Return radius */
    public double getRadius() {
        return radius;
    }

    /** Set a new radius */
    public void setRadius(double newRadius)
            throws InvalidRadiusException {
        if (newRadius >= 0)
            radius =  newRadius;
        else
            throw new InvalidRadiusException(newRadius);
    }

    /** Return numberOfObjects */
    public static int getNumberOfObjects() {
        return numberOfObjects;
    }

    /** Return the area of this circle */
    public double findArea() {
        return radius * radius * 3.14159;
    }
}
import java.util.*;

public class InputMismatchExceptionDemo {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        boolean continueInput = true;

        do {
            try {
                System.out.print("Enter an integer: ");
                int number = input.nextInt();

                // Display the result
                System.out.println(
                        "The number entered is " + number);

                continueInput = false;
            }
            catch (InputMismatchException ex) {
                System.out.println("Try again. (" +
                        "Incorrect input: an integer is required)");
                input.nextLine(); // discard input
            }
        } while (continueInput);
    }
}
public class InvalidRadiusException extends Exception {
    private double radius;

    /** Construct an exception */
    public InvalidRadiusException(double radius) {
        super("Invalid radius " + radius);
        this.radius = radius;
    }

    /** Return the radius */
    public double getRadius() {
        return radius;
    }
}
import java.util.Scanner;

public class Quotient {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        // Prompt the user to enter two integers
        System.out.print("Enter two integers: ");
        int number1 = input.nextInt();
        int number2 = input.nextInt();

        System.out.println(number1 + " / " + number2 + " is " +
                (number1 / number2));
    }
}
import java.util.Scanner;

public class QuotientWithException {
    public static int quotient(int number1, int number2) {
        if (number2 == 0)
            throw new ArithmeticException("Divisor cannot be zero");

        return number1 / number2;
    }

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        // Prompt the user to enter two integers
        System.out.print("Enter two integers: ");
        int number1 = input.nextInt();
        int number2 = input.nextInt();

        try {
            int result = quotient(number1, number2);
            System.out.println(number1 + " / " + number2 + " is "
                    + result);
        }
        catch (ArithmeticException ex) {
            System.out.println("Exception: an integer " +
                    "cannot be divided by zero ");
        }

        System.out.println("Execution continues ...");
    }
}
import java.util.Scanner;

public class QuotientWithIf {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        // Prompt the user to enter two integers
        System.out.print("Enter two integers: ");
        int number1 = input.nextInt();
        int number2 = input.nextInt();

        if (number2 != 0)
            System.out.println(number1 + " / " + number2 + " is " +
                    (number1 / number2));
        else
            System.out.println("Divisor cannot be zero ");
    }
}
import java.util.Scanner;

public class QuotientWithMethod {
    public static int quotient(int number1, int number2) {
        if (number2 == 0) {
            System.out.println("Divisor cannot be zero");
            System.exit(1);
        }

        return number1 / number2;
    }

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        // Prompt the user to enter two integers
        System.out.print("Enter two integers: ");
        int number1 = input.nextInt();
        int number2 = input.nextInt();

        int result = quotient(number1, number2);
        System.out.println(number1 + " / " + number2 + " is "
                + result);
    }
}
import java.util.Scanner;

public class ReadData {
    public static void main(String[] args) throws Exception {
        // Create a File instance
        java.io.File file = new java.io.File("scores.txt");

        // Create a Scanner for the file
        Scanner input = new Scanner(file);

        // Read data from a file
        while (input.hasNext()) {
            String firstName = input.next();
            String mi = input.next();
            String lastName = input.next();
            int score = input.nextInt();
            System.out.println(
                    firstName + " " + mi + " " + lastName + " " + score);
        }

        // Close the file
        input.close();
    }
}
import java.util.Scanner;

public class ReadFileFromURL {
    public static void main(String[] args) {
        System.out.print("Enter a URL: ");
        String URLString = new Scanner(System.in).next();

        try {
            java.net.URL url = new java.net.URL(URLString);
            int count = 0;
            Scanner input = new Scanner(url.openStream());
            while (input.hasNext()) {
                String line = input.nextLine();
                count += line.length();
            }

            System.out.println("The file size is " + count + " bytes");
        }
        catch (java.net.MalformedURLException ex) {
            System.out.println("Invalid URL");
        }
        catch (java.io.IOException ex) {
            System.out.println("IO Errors");
        }
    }
}
import java.util.Scanner;
import javax.swing.JFileChooser;

public class ReadFileUsingJFileChooser {
    public static void main(String[] args) throws Exception {
        JFileChooser fileChooser = new JFileChooser();
        if (fileChooser.showOpenDialog(null)
                == JFileChooser.APPROVE_OPTION) {
            // Get the selected file
            java.io.File file = fileChooser.getSelectedFile();

            // Create a Scanner for the file
            Scanner input = new Scanner(file);

            // Read text from the file
            while (input.hasNext()) {
                System.out.println(input.nextLine());
            }

            // Close the file
            input.close();
        }
        else {
            System.out.println("No file selected");
        }
    }
}
import java.io.*;
        import java.util.*;

public class ReplaceText {
    public static void main(String[] args) throws Exception {
        // Check command line parameter usage
        if (args.length != 4) {
            System.out.println(
                    "Usage: java ReplaceText sourceFile targetFile oldStr newStr");
            System.exit(1);
        }

        // Check if source file exists
        File sourceFile = new File(args[0]);
        if (!sourceFile.exists()) {
            System.out.println("Source file " + args[0] + " does not exist");
            System.exit(2);
        }

        // Check if target file exists
        File targetFile = new File(args[1]);
        if (targetFile.exists()) {
            System.out.println("Target file " + args[1] + " already exists");
            System.exit(3);
        }

        // Create input and output files
        Scanner input = new Scanner(sourceFile);
        PrintWriter output = new PrintWriter(targetFile);

        while (input.hasNext()) {
            String s1 = input.nextLine();
            String s2 = s1.replaceAll(args[2], args[3]);
            output.println(s2);
        }

        input.close();
        output.close();
    }
}
public class TestCircleWithCustomException {
    public static void main(String[] args) {
        try {
            new CircleWithCustomException(5);
            new CircleWithCustomException(-5);
            new CircleWithCustomException(0);
        }
        catch (InvalidRadiusException ex) {
            System.out.println(ex);
        }

        System.out.println("Number of objects created: " +
                CircleWithException.getNumberOfObjects());
    }
}

class CircleWithCustomException {
    /** The radius of the circle */
    private double radius;

    /** The number of the objects created */
    private static int numberOfObjects = 0;

    /** Construct a circle with radius 1 */
    public CircleWithCustomException() throws InvalidRadiusException {
        this(1.0);
    }

    /** Construct a circle with a specified radius */
    public CircleWithCustomException(double newRadius)
            throws InvalidRadiusException {
        setRadius(newRadius);
        numberOfObjects++;
    }

    /** Return radius */
    public double getRadius() {
        return radius;
    }

    /** Set a new radius */
    public void setRadius(double newRadius)
            throws InvalidRadiusException {
        if (newRadius >= 0)
            radius =  newRadius;
        else
            throw new InvalidRadiusException(newRadius);
    }

    /** Return numberOfObjects */
    public static int getNumberOfObjects() {
        return numberOfObjects;
    }

    /** Return the area of this circle */
    public double findArea() {
        return radius * radius * 3.14159;
    }
}
public class TestCircleWithException {
    public static void main(String[] args) {
        try {
            CircleWithException c1 = new CircleWithException(5);
            CircleWithException c2 = new CircleWithException(-5);
            CircleWithException c3 = new CircleWithException(0);
        }
        catch (IllegalArgumentException ex) {
            System.out.println(ex);
        }

        System.out.println("Number of objects created: " +
                CircleWithException.getNumberOfObjects());
    }
}
public class TestCircleWithRadiusException {
    /** Main method */
    public static void main(String[] args) {
        try {
            CircleWithRadiusException c1 = new CircleWithRadiusException(5);
            c1.setRadius(-5);
            CircleWithRadiusException c3 = new CircleWithRadiusException(0);
        }
        catch (InvalidRadiusException ex) {
            System.out.println(ex);
        }

        System.out.println("Number of objects created: " +
                CircleWithRadiusException.getNumberOfObjects());
    }
}
import java.util.Scanner;
import java.util.ArrayList;

public class WebCrawler {
    public static void main(String[] args) {
        java.util.Scanner input = new java.util.Scanner(System.in);
        System.out.print("Enter a URL: ");
        String url = input.nextLine();
        crawler(url); // Traverse the Web from the a starting url
    }

    public static void crawler(String startingURL) {
        ArrayList<String> listOfPendingURLs = new ArrayList<String>();
        ArrayList<String> listOfTraversedURLs = new ArrayList<String>();

        listOfPendingURLs.add(startingURL);
        while (!listOfPendingURLs.isEmpty() &&
                listOfTraversedURLs.size() <= 100) {
            String urlString = listOfPendingURLs.remove(0);
            if (!listOfTraversedURLs.contains(urlString)) {
                listOfTraversedURLs.add(urlString);
                System.out.println("Craw " + urlString);

                for (String s: getSubURLs(urlString)) {
                    if (!listOfTraversedURLs.contains(s))
                        listOfPendingURLs.add(s);
                }
            }
        }
    }

    public static ArrayList<String> getSubURLs(String urlString) {
        ArrayList<String> list = new ArrayList<String>();

        try {
            java.net.URL url = new java.net.URL(urlString);
            Scanner input = new Scanner(url.openStream());
            int current = 0;
            while (input.hasNext()) {
                String line = input.nextLine();
                current = line.indexOf("http:", current);
                while (current > 0) {
                    int endIndex = line.indexOf("\"", current);
                    if (endIndex > 0) { // Ensure that a correct URL is found
                        list.add(line.substring(current, endIndex));
                        current = line.indexOf("http:", endIndex);
                    }
                    else
                        current = -1;
                }
            }
        }
        catch (Exception ex) {
            System.out.println("Error: " + ex.getMessage());
        }

        return list;
    }
}
public class WriteData {
    public static void main(String[] args) throws Exception {
        java.io.File file = new java.io.File("scores.txt");
        if (file.exists()) {
            System.out.println("File already exists");
            System.exit(0);
        }

        // Create a file
        java.io.PrintWriter output = new java.io.PrintWriter(file);

        // Write formatted output to the file
        output.print("John T Smith ");
        output.println(90);
        output.print("Eric K Jones ");
        output.println(85);

        // Close the file
        output.close();
    }
}
public class CastingDemo {
    /** Main method */
    public static void main(String[] args) {
        // Create and initialize two objects
        Object object1 = new CircleFromSimpleGeometricObject(1);
        Object object2 = new RectangleFromSimpleGeometricObject(1, 1);

        // Display circle and rectangle
        displayObject(object1);
        displayObject(object2);
    }

    /** A method for displaying an object */
    public static void displayObject(Object object) {
        if (object instanceof CircleFromSimpleGeometricObject) {
            System.out.println("The circle area is " +
                    ((CircleFromSimpleGeometricObject)object).getArea());
            System.out.println("The circle diameter is " +
                    ((CircleFromSimpleGeometricObject)object).getDiameter());
        }
        else if (object instanceof
                RectangleFromSimpleGeometricObject) {
            System.out.println("The rectangle area is " +
                    ((RectangleFromSimpleGeometricObject)object).getArea());
        }
    }
}
public class CircleFromSimpleGeometricObject
        extends SimpleGeometricObject {
    private double radius;

    public CircleFromSimpleGeometricObject() {
    }

    public CircleFromSimpleGeometricObject(double radius) {
        this.radius = radius;
    }

    public CircleFromSimpleGeometricObject(double radius,
                                           String color, boolean filled) {
        this.radius = radius;
        setColor(color);
        setFilled(filled);
    }

    /** Return radius */
    public double getRadius() {
        return radius;
    }

    /** Set a new radius */
    public void setRadius(double radius) {
        this.radius = radius;
    }

    /** Return area */
    public double getArea() {
        return radius * radius * Math.PI;
    }

    /** Return diameter */
    public double getDiameter() {
        return 2 * radius;
    }

    /** Return perimeter */
    public double getPerimeter() {
        return 2 * radius * Math.PI;
    }

    /* Print the circle info */
    public void printCircle() {
        System.out.println("The circle is created " + getDateCreated() +
                " and the radius is " + radius);
    }
}
import java.util.ArrayList;
import java.util.Scanner;

public class DistinctNumbers {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<Integer>();

        Scanner input = new Scanner(System.in);
        System.out.print("Enter integers (input ends with 0): ");
        int value;

        do {
            value = input.nextInt(); // Read a value from the input

            if (!list.contains(value) && value != 0)
                list.add(value); // Add the value if it is not in the list
        } while (value != 0);

        // Display the distinct numbers
        for (int i = 0; i < list.size(); i++)
            System.out.print(list.get(i) + " ");
    }
}
public class DynamicBindingDemo {
    public static void main(String[] args) {
        Object o = new GraduateStudent(); // implicit casting

        Object o1 = new Object();

        if (o1 instanceof GraduateStudent) {
            System.out.println("Never got here");
            GraduateStudent gs = (GraduateStudent)o1; // explicit casting
        }

        m(o);
        m(new Student());
        m(new Person());
        m(new Object());
    }

    public static void m(Object x) {
        System.out.println(x.toString());
    }
}

class GraduateStudent extends Student {
}

class Student extends Person {
    @Override
    public String toString() {
        return "Student";
    }
}

class Person extends Object {
    @Override
    public String toString() {
        return "Person";
    }
}
public abstract class GeometricObject {
    private String color = "white";
    private boolean filled;
    private java.util.Date dateCreated;

    /** Construct a default geometric object */
    protected GeometricObject() {
        dateCreated = new java.util.Date();
    }

    /** Construct a geometric object with color and filled value */
    protected GeometricObject(String color, boolean filled) {
        dateCreated = new java.util.Date();
        this.color = color;
        this.filled = filled;
    }

    /** Return color */
    public String getColor() {
        return color;
    }

    /** Set a new color */
    public void setColor(String color) {
        this.color = color;
    }

    /** Return filled. Since filled is boolean,
     *  the get method is named isFilled */
    public boolean isFilled() {
        return filled;
    }

    /** Set a new filled */
    public void setFilled(boolean filled) {
        this.filled = filled;
    }

    /** Get dateCreated */
    public java.util.Date getDateCreated() {
        return dateCreated;
    }

    @Override
    public String toString() {
        return "created on " + dateCreated + "\ncolor: " + color +
                " and filled: " + filled;
    }

    /** Abstract method getArea */
    public abstract double getArea();

    /** Abstract method getPerimeter */
    public abstract double getPerimeter();
}
import java.util.ArrayList;

public class MyStack {
    private ArrayList<Object> list = new ArrayList<Object>();

    public boolean isEmpty() {
        return list.isEmpty();
    }

    public int getSize() {
        return list.size();
    }

    public Object peek() {
        return list.get(getSize() - 1);
    }

    public Object pop() {
        Object o = list.get(getSize() - 1);
        list.remove(getSize() - 1);
        return o;
    }

    public void push(Object o) {
        list.add(o);
    }

    @Override /** Override the toString in the Object class */
    public String toString() {
        return "stack: " + list.toString();
    }
}
public class RectangleFromSimpleGeometricObject
        extends SimpleGeometricObject {
    private double width;
    private double height;

    public RectangleFromSimpleGeometricObject() {
    }

    public RectangleFromSimpleGeometricObject(
            double width, double height) {
        this.width = width;
        this.height = height;
    }

    public RectangleFromSimpleGeometricObject(
            double width, double height, String color, boolean filled) {
        this.width = width;
        this.height = height;
        setColor(color);
        setFilled(filled);
    }

    /** Return width */
    public double getWidth() {
        return width;
    }

    /** Set a new width */
    public void setWidth(double width) {
        this.width = width;
    }

    /** Return height */
    public double getHeight() {
        return height;
    }

    /** Set a new height */
    public void setHeight(double height) {
        this.height = height;
    }

    /** Return area */
    public double getArea() {
        return width * height;
    }

    /** Return perimeter */
    public double getPerimeter() {
        return 2 * (width + height);
    }
}
import java.util.ArrayList;

public class TestArrayList {
    public static void main(String[] args) {
        // Create a list to store cities
        ArrayList<String> cityList = new ArrayList<String>();

        // Add some cities in the list
        cityList.add("London");
        // cityList now contains [London]
        cityList.add("Denver");
        // cityList now contains [London, Denver]
        cityList.add("Paris");
        // cityList now contains [London, Denver, Paris]
        cityList.add("Miami");
        // cityList now contains [London, Denver, Paris, Miami]
        cityList.add("Seoul");
        // contains [London, Denver, Paris, Miami, Seoul]
        cityList.add("Tokyo");
        // contains [London, Denver, Paris, Miami, Seoul, Tokyo]

        System.out.println("List size? " + cityList.size());
        System.out.println("Is Miami in the list? " +
                cityList.contains("Miami"));
        System.out.println("The location of Denver in the list? "
                + cityList.indexOf("Denver"));
        System.out.println("Is the list empty? " +
                cityList.isEmpty()); // Print false

        // Insert a new city at index 2
        cityList.add(2, "Xian");
        // contains [London, Denver, Xian, Paris, Miami, Seoul, Tokyo]

        // Remove a city from the list
        cityList.remove("Miami");
        // contains [London, Denver, Xian, Paris, Seoul, Tokyo]

        // Remove a city at index 1
        cityList.remove(1);
        // contains [London, Xian, Paris, Seoul, Tokyo]

        // Display the contents in the list
        System.out.println(cityList.toString());

        // Display the contents in the list in reverse order
        for (int i = cityList.size() - 1; i >= 0; i--)
            System.out.print(cityList.get(i) + " ");
        System.out.println();

        // Create a list to store two circles
        java.util.ArrayList<CircleFromSimpleGeometricObject> list
                = new java.util.ArrayList<CircleFromSimpleGeometricObject>();

        // Add two circles
        list.add(new CircleFromSimpleGeometricObject(2));
        list.add(new CircleFromSimpleGeometricObject(3));

        // Display the area of the first circle in the list
        System.out.println("The area of the circle? " +
                ((CircleFromSimpleGeometricObject)list.get(0)).getArea());
    }
}
public class TestCircleRectangle {
    public static void main(String[] args) {
        CircleFromSimpleGeometricObject circle =
                new CircleFromSimpleGeometricObject(1);
        System.out.println("A circle " + circle.toString());
        System.out.println("The color is " + circle.getColor());
        System.out.println("The radius is " + circle.getRadius());
        System.out.println("The area is " + circle.getArea());
        System.out.println("The diameter is " + circle.getDiameter());

        RectangleFromSimpleGeometricObject rectangle =
                new RectangleFromSimpleGeometricObject(2, 4);
        System.out.println("\nA rectangle " + rectangle.toString());
        System.out.println("The area is " + rectangle.getArea());
        System.out.println("The perimeter is " +
                rectangle.getPerimeter());
    }
}
