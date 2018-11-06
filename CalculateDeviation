import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.MouseEvent;
import java.awt.event.MouseListener;
import java.awt.event.MouseMotionListener;
import java.util.ArrayList;
import java.util.Random;

import javax.swing.*;
 
public class DrawLine extends JPanel {	
	
  private static final long serialVersionUID = 1L;
    
  LinePoint[] lineACordsList = new LinePoint[100];
  LinePoint[] lineBCordsList = new LinePoint[100];
	
  public void paintComponent(Graphics g) {
 
     for(int i = 0; i < lineACordsList.length; i++) {
    	 lineACordsList[i] =  new LinePoint();
    	 lineBCordsList[i] =  new LinePoint();
     }
     
     Random random = new Random();
     int initialLocationPoint = 10;
     for(int i = 0; i<lineACordsList.length; i++) {
    	 lineACordsList[i].x = initialLocationPoint;
         lineACordsList[i].y = 100;
         lineBCordsList[i].x = initialLocationPoint;
         lineBCordsList[i].y = 105;
         
         g.drawOval((int)lineACordsList[i].x, (int)lineACordsList[i].y, 1, 1);
         g.drawOval((int)lineBCordsList[i].x, (int)lineBCordsList[i].y, 1, 1);
         
         initialLocationPoint +=1; 
     }
     
     System.out.println("DEVIATION: " + this.calculateDifference());
 
  }
  
  public double calculateDifference() {
	  double deviation = 0.0;
	  double deviationPerCordinateUsingPitagoraFormula = 0.0;
	  for (int i = 0; i < lineACordsList.length; i++) {
		  deviationPerCordinateUsingPitagoraFormula = Math.sqrt( Math.pow((lineBCordsList[i].x - lineACordsList[i].x), 2)  + Math.pow((lineBCordsList[i].y - lineACordsList[i].y), 2));
		  deviation = deviation + deviationPerCordinateUsingPitagoraFormula;
	  }
	  return deviation;
  }
 
  public static void main(String[] args) {
    JFrame.setDefaultLookAndFeelDecorated(true);
    
    JFrame frame = new JFrame("Calculate the deviation/distance between a set of cords");
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setBackground(Color.white);
    frame.setSize(400, 400);
 
    DrawLine panel = new DrawLine();
    frame.add(panel);
    frame.setVisible(true);
  }
}

class LinePoint
{
    double x;
    double y;
}
