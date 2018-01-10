# Tic_Tac_Toe_GUI
An interactive tic-Tac-Toe game that uses GUI and is coded in JAVA 
/**
 * The GUI from the notes (p.15 Chapter 11 Slides)
 * 
 * @author Lynn Marshall
 * @version Skeleton: November 17, 2012
 * 
 * @author Shoana Sharma
 * @version December 5, 2017
 */
import java.awt.*;
import javax.swing.*;
import java.awt.event.*;
import java.util.*;

import javax.swing.border.TitledBorder;
import javax.swing.border.Border;
import javax.swing.border.EtchedBorder;
import java.awt.Component; // panel
import javax.swing.GroupLayout.*;
import javax.swing.event.*;

public class NotesGui implements ActionListener
{

    private TitledBorder titleButtons = BorderFactory.createTitledBorder(BorderFactory.createEtchedBorder(EtchedBorder.LOWERED), "Buttons");

    //initialze J buttons
    private JPanel buttonPanel1 = new JPanel();
    private JPanel buttonPanel2 = new JPanel();
    private Border titleButton = BorderFactory.createEtchedBorder(EtchedBorder.LOWERED);
    private JPanel buttonPanel3 = new JPanel();
    private JButton jButton = new JButton("A JButton");
    private JToggleButton jToggleButton = new JToggleButton("A JToggleButton");

    // initialize Checkboxes
    private Border titleCheckButton = BorderFactory.createEtchedBorder(EtchedBorder.LOWERED);
    private JPanel checkBoxPanel = new JPanel();
    private JCheckBox check1 = new JCheckBox("A JCheckBox");
    private JCheckBox check2 = new JCheckBox("Another JCheckBox");

    // initialize Radio buttons
    private TitledBorder titleRadioButton = BorderFactory.createTitledBorder("A ButtonGroup");
    private JPanel radioPanel = new JPanel();
    private ButtonGroup radioGroup = new ButtonGroup();
    private JRadioButton radioB1 = new JRadioButton("A JRadioButton");
    private JRadioButton radioB2 = new JRadioButton("Another JRadioButton");

    // initialize Text Area
    private TitledBorder titleText = BorderFactory.createTitledBorder(BorderFactory.createEtchedBorder(EtchedBorder.LOWERED), "Labels and Text Entry");
    private JPanel textPanel1 = new JPanel();
    private JPanel textPanel2 = new JPanel();
    private JLabel label = new JLabel("A JLabel with a text label.");
    private JTextField textField = new JTextField("You can type text in an editable JTextField");

    // initialize Progress Bar
    private TitledBorder titlePBar = BorderFactory.createTitledBorder(BorderFactory.createEtchedBorder(EtchedBorder.LOWERED), "A JProgress Bar");
    private JProgressBar progressBar = new JProgressBar();
    private JPanel pBPanel1 = new JPanel();
    private JPanel pBPanel2 = new JPanel();

    // initialize Componenets
    private TitledBorder titleComponent = BorderFactory.createTitledBorder(BorderFactory.createEtchedBorder(EtchedBorder.LOWERED), "Components for Selecting");
    private JPanel componentPanel1 = new JPanel();
    private JPanel componentPanel2 = new JPanel();

    // initialize Slider
    private TitledBorder titleSlider = BorderFactory.createTitledBorder(BorderFactory.createEtchedBorder(EtchedBorder.LOWERED), "A JSlider");
    private JPanel sliderPanel = new JPanel ();
    private JSlider jslider = new JSlider (JSlider.HORIZONTAL, 0, 10, 0);

    // initialize Spinner 
    private TitledBorder titleSpinner = BorderFactory.createTitledBorder(BorderFactory.createEtchedBorder(EtchedBorder.LOWERED), "A JSpinner");
    private JPanel spinnerPanel = new JPanel ();
    private JSpinner jspinner = new JSpinner ();
    
    String[] list = { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5", "Item 6","Item 7", "Item 8", "Item 9", "Item 10"};
    
    // initialize Combo box
    private TitledBorder titleComboBox = BorderFactory.createTitledBorder(BorderFactory.createEtchedBorder(EtchedBorder.LOWERED), "A JComboBox");
    private JPanel comboBoxPanel = new JPanel ();
    private JComboBox comboBox = new JComboBox(list);

    // initialize J List
    private TitledBorder titleList = BorderFactory.createTitledBorder(BorderFactory.createEtchedBorder(EtchedBorder.LOWERED), "A JList in a JScroll Pane");
    private JList jlist = new JList();

    private JScrollPane jScrollPane = new JScrollPane(jlist);
    private JPanel panelL1 = new JPanel();
    private JPanel panelL2 = new JPanel();

    public NotesGui() {
        // JFrame and contentPane
        JFrame frame = new JFrame("Swing Component Demo");
        Container contentPane = frame.getContentPane();

        // set the layout of the contentPane
        
        buttonPanel2.setLayout(new GridLayout(1,1));

        buttonPanel3.setLayout (new BoxLayout(buttonPanel3,BoxLayout.PAGE_AXIS));

        buttonPanel3.add(jButton);
        buttonPanel3.add(jToggleButton);

        checkBoxPanel.setLayout (new BoxLayout(checkBoxPanel,BoxLayout.PAGE_AXIS));
        checkBoxPanel.add(check1);
        checkBoxPanel.add(check2);

        radioPanel.setLayout (new BoxLayout(radioPanel,BoxLayout.PAGE_AXIS));
        radioPanel.add(radioB1);
        radioPanel.add(radioB2);
        // radioGroup.add(radioB1);
        // radioGroup.add(radioB2);

        buttonPanel1.add(buttonPanel3);
        buttonPanel1.add(radioPanel);
        buttonPanel1.add(checkBoxPanel);

        
        

        JPanel bottomP1 = new JPanel();
        JPanel bottomP2 = new JPanel();
        JPanel bottomP3 = new JPanel();
        JPanel bottomP4 = new JPanel();
       

        
        GroupLayout layout = new GroupLayout(componentPanel1);
        componentPanel1.setLayout(layout);
        layout.setAutoCreateGaps(true);

        GroupLayout.SequentialGroup seqGroup1 = layout.createSequentialGroup();
        seqGroup1.addGroup(layout.createParallelGroup().addComponent(bottomP1).addComponent(bottomP3));
        seqGroup1.addGroup(layout.createParallelGroup().addComponent(bottomP2).addComponent(bottomP4));        
        layout.setHorizontalGroup(seqGroup1);

        GroupLayout.SequentialGroup seqGroup2 = layout.createSequentialGroup();
        seqGroup2.addGroup(layout.createParallelGroup(Alignment.BASELINE).addComponent(bottomP1).addComponent(bottomP2));
        seqGroup2.addGroup(layout.createParallelGroup(Alignment.BASELINE).addComponent(bottomP3).addComponent(bottomP4));
        layout.setVerticalGroup(seqGroup2);

        // adding Panels to respective Borders
        
        addToBorder(titleButtons, buttonPanel1, buttonPanel2);

        
       
        spinnerPanel.add(jspinner);

        comboBoxPanel.add(comboBox);
        

        JPanel all = new JPanel();
        all.setLayout(new BoxLayout(all, BoxLayout.Y_AXIS));

        all.add(buttonPanel2);
        all.add(textPanel2);
        //all.add(panelL2);
        all.add(pBPanel2);
        all.add(componentPanel2);
        
        
        frame.add(all);

        jButton.addActionListener(this);
        jToggleButton.addActionListener(this);
        check1.addActionListener(this);
        check2.addActionListener(this);
        comboBox.addActionListener(this);
        textField.addActionListener(this);
        radioB1.addActionListener(this);
        radioB2.addActionListener(this);

        // finish setting up the frame
        frame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);
        frame.pack();
        frame.setResizable(true);
        frame.setVisible(true);
    }

    
    /** 
     * Method addToBorder adds Panels (and other components) to a given Border
     * 
     * @param Border in which component will be added to
     * @param Component description Desciprion of compnent added to border
     * @param Conatiner  of border
     * 
     */
    public void addToBorder(Border border, Component description, Container container){
        JPanel newPanel = new JPanel(new GridLayout(1, 1), false);
        newPanel.add(description);
        container.add(newPanel);
        newPanel.setBorder(border);
    }

    /** 
     * This action listener is called when the user clicks / enters
     * information using the GUI. 
     */
    public void actionPerformed(ActionEvent e)
    {
        Object o = e.getSource();
        if (o instanceof JButton){ 
            System.out.println("JButton has been clicked."); 
        }
        
    }    
}
