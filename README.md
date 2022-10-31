# guessing-game-
import java.awt.*;
import java.awt.event.*;
import java.util.Random;

public class guessnumber extends Frame {
	int guess=0;
	int rand;
	private Label l3;
	private Button b1;
	private Button b2;
	private TextArea a;
	private TextField t2;
	private TextField t1;
	guessnumber()
	{
		addWindowListener(new WindowAdapter() {
			public void windowClosing(WindowEvent we)
			{
				System.exit(0);
			}
		});
		setLayout(null);
		Font f1= new Font("Arial",Font.PLAIN,50) ;
		Label l1=new Label("1.2.3.");
		add(l1);
		l1.setBounds(200,40,150,50);
		l1.setFont(f1);
		l1.setForeground(Color.decode("#FFDEAD"));
		
		Label l2=new Label("Guess a number between 0-100");
		add(l2);
		l2.setBounds(100,120,300,30);
		l2.setForeground(Color.blue);
		
		TextField t1=new TextField(12);
		add(t1);
		t1.setBounds(100,160,300,30);
	    Label l3=new Label();
		add(l3);
		l3.setBounds(100,200,300,30);
		l3.setBackground(Color.decode("#FFE4B5"));
		l3.setForeground(Color.decode("#8B4513"));
       

		Button b1=new Button("Check Me");
		Button b2=new Button("Restart");
		add(b1);
		add(b2);
		b1.setBounds(150,240,80,30);
		b2.setBounds(250,240,50,30);
		b1.setBackground(Color.decode("#696969"));
		b1.setForeground(Color.white);
		b2.setBackground(Color.decode("#A9A9A9"));
		TextArea a=new TextArea(1,20);
		add(a);
		a.setBounds(100,280,300,300);
		
		b1.addActionListener(new ActionListener() {
			 public void actionPerformed(ActionEvent e) {
					guess=Integer.parseInt(t1.getText());
			        if (e.getSource()==b1){
			        	rand=new Random().nextInt(100)+1;
			            a.append("You guessed "+guess+"\n");
			            if(guess<=0||guess>100){
			                l3.setText("Your guess is INVALID");
			            }
			            else if(guess==rand){
			                l3.setText("Correct guess.Number="+rand);
			            }
			            else if(guess > rand){
			                l3.setText("Your guess is too HIGH.Try Again");
			            }
			            else if(guess < rand){
			                l3.setText("Your guess is too LOW.Try Again");
			            }
			            else{
			                l3.setText("Your guess is INCORRECT.Try again");
			            }
			        }
			 }       
		});
	   
		b2.addActionListener(new ActionListener() {
			 public void actionPerformed(ActionEvent e) {
					guess=Integer.parseInt(t1.getText());
				if (e.getSource()==b2){
		            rand=new Random().nextInt(100)+1;
		            a.setText(null);
		            l3.setText("");
		            t1.setText("");
		        }
			 }	
		});
	
		setVisible(true);
		setSize(500,700);
		setTitle("Guessing Game");
		setResizable(false);
		

    }
	public static void main(String[] args)
	{
		guessnumber g=new guessnumber();
	}
 
	
                

	}
