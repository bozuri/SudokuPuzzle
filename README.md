
import java.awt.BorderLayout;
import java.awt.Color;
import java.awt.EventQueue;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.JTextField;
import javax.swing.border.EmptyBorder;
import java.awt.GridLayout;
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;
import java.nio.file.*;


public class Sudoku extends JFrame {

	private JPanel contentPane;
	private JTextField gameButtons;
	private static JTextField[] board = new JTextField[81];
	/**
	 * Launch the application.
	 * @throws FileNotFoundException 
	 */
	public static void main(String[] args) throws FileNotFoundException {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					Sudoku frame = new Sudoku();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
		int currVal = 0;
		Scanner testPuzzle = new Scanner(new File("Test1"));
		for(int i=0;i<81;i++){
			currVal = testPuzzle.nextInt();
			board[i] = new JTextField();
			board[i].setBackground(Color.WHITE);
			board[i].setText(currVal + "");
		}
	}

	/**
	 * Create the frame.
	 */
	public Sudoku() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 500, 500);
		contentPane = new JPanel();
		contentPane.setBackground(Color.LIGHT_GRAY);
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(new GridLayout(9, 9, 0, 0));
	}

}
