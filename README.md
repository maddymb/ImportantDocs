package com.programs;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JOptionPane;
import javax.swing.JPanel;
import javax.swing.JTextField; 
public class swing {
    
    public static void main(String[] args) {    
        // Creating instance of JFrame
        JFrame frame = new JFrame("Resetting Member Number");
        // Setting the width and height of frame
        frame.setSize(380,180);
        frame.setResizable(false);
        frame.setLocationRelativeTo(null); 
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        /* Creating panel. This is same as a div tag in HTML
         * We can create several panels and add them to specific 
         * positions in a JFrame. Inside panels we can add text 
         * fields, buttons and other components.
         */
        JPanel panel = new JPanel();    
        // adding panel to frame
        frame.add(panel);
        /* calling user defined method for adding components
         * to the panel.
         */
        placeComponents(panel);

        // Setting the frame visibility to true
        frame.setVisible(true);
    }


    
    private static void placeComponents(JPanel panel) {

        /* We will discuss about layouts in the later sections
         * of this tutorial. For now we are setting the layout 
         * to null
         */
        panel.setLayout(null);

        // Creating JLabel
        JLabel userLabel = new JLabel("Enter Member Number");
        /* This method specifies the location and size
         * of component. setBounds(x, y, width, height)
         * here (x,y) are cordinates from the top left 
         * corner and remaining two arguments are the width
         * and height of the component.
         */
        userLabel.setBounds(10,20,150,25);
        panel.add(userLabel);

        /* Creating text field where user is supposed to
         * enter user name.
         */
        JTextField userText = new JTextField(20);
        userText.setBounds(170,20,165,25);
        panel.add(userText);

     

        // Creating login button
        JButton loginButton = new JButton("Reset Member Number");
        loginButton.setBounds(90, 80, 180, 25);
        panel.add(loginButton);
        
        loginButton.addActionListener(new ActionListener() { 
            public void actionPerformed(ActionEvent e) {
             String member= userText.getText();
            	
            	
            	System.out.println("Member Number "+member);
            	if(member.equalsIgnoreCase("1")) {
            		
            	System.err.println("fghv");
            	JOptionPane.showMessageDialog(null, "Member Number Sucessfully Reset");
            	userText.setText("");
            	
            	}
            	
            	else
            		JOptionPane.showMessageDialog(null, "Not Able To Reset Member Number");
            		
            }
          }); 
        
    }

}
