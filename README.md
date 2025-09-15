import javax.swing.JOptionPane;
import javax.swing.*;
import java.util.*;
import java.lang.*;

class Main {
  public static void main(String[] args) {
    
    int num=Integer.parseInt(JOptionPane.showInputDialog("Enter a radical."));

    int posorneg=1;
    
    if(num<0)
    {
      posorneg=-1;
      num=num*-1;
    }
    double sqrt=Math.sqrt(num);

    if(sqrt%1==0)
    {
    JOptionPane.showMessageDialog(null,(posorneg>=0 ? (int)sqrt : (int)sqrt+"i"));
    }
    
    if(sqrt%1!=0)
      {
        ArrayList factors=new ArrayList();
        int wholenum=1;
        
        for(int i=1;i<=num;i++)
          {
            if(num%(i*i)==0)
            {
              factors.add(i);
              wholenum=wholenum*i;
              num=num/(i*i);
            }
          }

          JOptionPane.showMessageDialog(null,(posorneg>=0 ?  wholenum + " √"+num : wholenum + "i √"+num));

        
          }
    
  }
}
