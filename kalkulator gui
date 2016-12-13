import java.awt.*;
import java.awt.event.*;
import java.io.*;
import javax.swing.*;
import java.sql.*;
import javax.swing.table.DefaultTableModel;
 class calc extends JFrame implements ActionListener
{
    private JPanel         pBrg       = new JPanel();
    private JLabel         l1         = new JLabel ("1"),
                        lSama      	= new JLabel ("Jumlah      "),
                        lnama        = new JLabel ("KALKULATOR");
                        
    private JTextField     fLayar       = new JTextField (); 

    private JButton     btnTambah     = new JButton (), 
                        btnKurang      = new JButton (), 
                        btnKali       = new JButton (),
                        btnBagi           = new JButton (),
                        btnPersen      = new JButton (),
                        btnKoma      = new JButton (),
                        btnOff      = new JButton (),
                        btnOn      = new JButton (),
                        btnBack      = new JButton (),
                        btnMinus      = new JButton (),
                        btnPangkat       = new JButton (),
                        btnBagi1       = new JButton (),
                        btn00  = new JButton (), 
                        btn0  = new JButton (), 
                        btn1  = new JButton (), 
                        btn2  = new JButton (), 
                        btn3  = new JButton (), 
                        btn4  = new JButton (),
                        btn5  = new JButton (),
                        btn6  = new JButton (),
                        btn7  = new JButton (),
                        btn8  = new JButton (),
                        btn9  = new JButton (),
                        btnSama  = new JButton ();
    
    private String isiLayar = "";
    private String snilai1, snilai2, tombol,bukan_angka;
    private int hasil;
    boolean angka_baru = false;
                    
    public calc() {
        setPreferredSize(new Dimension(400,550));
        setTitle("Kalkulator");
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        new BorderLayout();
        JDesktopPane pBrg = new JDesktopPane();
        add(pBrg, BorderLayout.CENTER);
        pBrg.setBackground(Color.gray);
        
        /* Mengatur letak objek Text Di Container */
        fLayar.setBounds (50, 40, 280, 30);
        lnama.setBounds (150, 1, 200, 50);

        /* Mengatur letak objek Button di Container */
        //btnOff.setBounds (50, 100, 85, 40);    
        //btnOff.setLabel("Exit");
        btnOn.setBounds (50, 400, 50, 40);    
        btnOn.setLabel("C");
        btnTambah.setBounds (50, 100, 50, 40);    
        btnTambah.setLabel("+");
        btnKurang.setBounds (100, 100, 50, 40);    
        btnKurang.setLabel("-");
        btnKali.setBounds (150, 100, 50, 40);    
        btnKali.setLabel("*");
        btnBagi.setBounds (200, 100, 50, 40);    
        btnBagi.setLabel("/");
        btnBack.setBounds (100, 400, 100, 40);    
        btnBack.setLabel("Backspace");
        btnSama.setBounds (250, 160, 75, 200);    
        btnSama.setLabel("hasil");
        btnSama.setFont(new Font("Times New Roman", 10, 20));
        //btnKoma.setBounds (250,310, 85, 40);    
        //btnKoma.setLabel(".");
        btnPersen.setBounds (250, 100, 60, 40);
        btnPersen.setLabel("mod");
       /* btnPangkat.setBounds (350, 410, 85, 40);
        btnPangkat.setLabel("x^y");
        btnBagi1.setBounds (250, 410, 85, 40);
        btnBagi1.setLabel("1/x");*/ 
        btnMinus.setBounds (200, 400, 60, 40);    
        btnMinus.setLabel("( - )");                                   

        //btnAdd.setToolTipText("Tombol Tambah Data");
        btn7.setBounds (50, 160, 50, 40);
        btn7.setLabel("7");
        btn8.setBounds (110, 160, 50, 40);
        btn8.setLabel("8");
        btn9.setBounds (170, 160, 50, 40);
        btn9.setLabel("9");
        btn4.setBounds (50, 210, 50, 40);
        btn4.setLabel("4");
        btn5.setBounds (110, 210, 50, 40);
        btn5.setLabel("5");
        btn6.setBounds (170, 210, 50, 40);
        btn6.setLabel("6");
        btn1.setBounds (50, 260, 50, 40);
        btn1.setLabel("1");
        btn2.setBounds (110, 260, 50, 40);
        btn2.setLabel("2");
        btn3.setBounds (170, 260, 50, 40);
        btn3.setLabel("3");
        btn0.setBounds (110, 310, 50, 40);
        btn0.setLabel("0");
        //btn00.setBounds (50, 310, 85, 40);
        //btn00.setLabel("00");
        
        fLayar.setHorizontalAlignment (JTextField.RIGHT);   
        /* Objek Button di Non Aktifkan dan di aktifkan */
        btnTambah.setEnabled(true);        
        btnKurang.setEnabled(true);
        btnKali.setEnabled(true);
        btnBagi.setEnabled(true);
        btnSama.setEnabled(true);
        btnBack.setEnabled(true);
        btnPersen.setEnabled(true);        
        btnMinus.setEnabled(true);    
        btnPangkat.setEnabled(true);
        btnBagi1.setEnabled(true);        

        /* Mengatur objek untuk dapat berinteraksi */
        //btn1.addActionListener (this);
        //btn2.addActionListener (this);
        btn3.addActionListener (this);
        btn4.addActionListener (this);
        btn5.addActionListener (this);
        btn6.addActionListener (this);
        btn7.addActionListener (this);
        btn8.addActionListener (this);
        btn9.addActionListener (this);
        btn0.addActionListener (this);
        btn00.addActionListener (this);

        btnTambah.addActionListener (this);
        btnKurang.addActionListener (this);
        btnKali.addActionListener (this);
        btnBagi.addActionListener (this);
        btnSama.addActionListener (this);
        btnKoma.addActionListener (this);
        btnOff.addActionListener (this);
        btnOn.addActionListener (this);
        btnBack.addActionListener (this);
        btnPersen.addActionListener (this);
        btnMinus.addActionListener (this);
        btnPangkat.addActionListener (this);
        btnBagi1.addActionListener (this);
        
        // Meletakkan seluruh kontrol pada objek panel */
        pBrg.add (fLayar);
        pBrg.add (btn1);
        pBrg.add (btn2);
        pBrg.add (btn3);
        pBrg.add (btn4);
        pBrg.add (btn5);
        pBrg.add (btn6);
        pBrg.add (btn7);
        pBrg.add (btn8);
        pBrg.add (btn9);
        pBrg.add (btn0);
        pBrg.add (btn00);

        pBrg.add (btnOff);
        pBrg.add (btnOn);
        pBrg.add (btnTambah);        
        pBrg.add (btnKurang);    
        pBrg.add (btnSama);
        pBrg.add (btnKali);
        pBrg.add (btnBagi);
        pBrg.add (btnKoma);
        pBrg.add (btnBack);
        pBrg.add (btnPersen);
        pBrg.add (btnMinus);
        pBrg.add (btnPangkat);
        pBrg.add (btnBagi1);
        pBrg.add (lnama);
        /* Menambahkan objek panel (pBrg) ke container frame */
        //getContentPane().add (pBrg);
        
        /* Menampilkan frame ke layar monitor */
        pack();
        setVisible (true);
        setLocationRelativeTo(null);
    }
    
    public static void main(String[] args) {
        new calc().setVisible(true);
    }
    
    /* Fungsi jika user melakukan action penekanan tombol Button */
    public void actionPerformed (ActionEvent ae) {
    	try {
        Object obj = ae.getSource();
        String a = ae.getActionCommand();      
        if (obj == btn1)
            { 
                 isiLayar = isiLayar + "1";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btn2)     
            { 
                 isiLayar = isiLayar + "2";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btn3)     
            { 
                 isiLayar = isiLayar + "3";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btn4)     
            { 
                 isiLayar = isiLayar + "4";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btn5)     
            { 
                 isiLayar = isiLayar + "5";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btn6)     
            { 
                 isiLayar = isiLayar + "6";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btn7)     
            { 
                 isiLayar = isiLayar + "7";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btn8)     
            { 
                 isiLayar = isiLayar + "8";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btn9)     
            { 
                 isiLayar = isiLayar + "9";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btn0)     
            { 
                 isiLayar = isiLayar + "0";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btn00)     
            { 
                 isiLayar = isiLayar + "00";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btnKoma)     
            { 
                 isiLayar = isiLayar + ".";
                 fLayar.setText(isiLayar); 
            }
            
        if (obj == btnTambah)     
            { 
                tombol = "tambah";
                snilai1 = fLayar.getText();
                isiLayar = "";
                 fLayar.setText(isiLayar); 

            }                
        if (obj == btnKurang)     
            { 
                tombol = "kurang";
                snilai1 = fLayar.getText();
                isiLayar = "";
                 fLayar.setText(isiLayar);                 
            }
        if (obj == btnKali)     
            { 
                tombol = "kali";
                snilai1 = fLayar.getText();
                isiLayar = "";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btnBagi)     
            { 
                tombol = "bagi";
                snilai1 = fLayar.getText();
                isiLayar = "";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btnPersen)     
            { 
                tombol = "persen";
                snilai1 = fLayar.getText();
                isiLayar = "";
                 fLayar.setText(isiLayar); 
                 
                 if(tombol == "persen")
                {                    
                snilai2 = fLayar.getText();
                Float hasil = Float.parseFloat(snilai1) / 100;
                String shasil = ""+hasil;
                fLayar.setText(shasil);
                isiLayar = ("");
                } 
            }
        if (obj == btnMinus)     
            { 
                 isiLayar = isiLayar + "-";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btnPangkat)     
            { 
                tombol = "pangkat";
                snilai1 = fLayar.getText();
                isiLayar = "";
                 fLayar.setText(isiLayar); 
            }
        if (obj == btnBagi1)     
            { 
                tombol = "bagi1";
                snilai1 = fLayar.getText();
                isiLayar = "";
                 fLayar.setText(isiLayar);
                 
                 if(tombol == "bagi1")
                {                    
                snilai2 = fLayar.getText();
                Float hasil = 1 / Float.parseFloat(snilai1);
                String shasil = ""+hasil;
                fLayar.setText(shasil);
                isiLayar = ("");
                }     
            }                       
        if(obj == btnOff)
        {
            this.dispose();
        }
        
        if(obj == btnOn)
        {
            On();
        }
        
        if (obj == btnSama)     
            {             
                Sama();
               }
        if (obj == btnBack)
        {
            
            {
                if (fLayar.getText().length() > 0)
                   fLayar.setText(fLayar.getText().substring(0, fLayar.getText().length() - 1));
            
                else
                 
                JOptionPane.showMessageDialog(null, "Tidak ada angka yang bisa dihapus", 
                "Kesalahan", JOptionPane.WARNING_MESSAGE);
            }
        } else if (fLayar.getText().) { throw new NumberFormatException(); }
        } catch(NumberFormatException e) {
        	JOptionPane.showMessageDialog(null, "inputan tidak boleh huruf", 
                "Kesalahan", JOptionPane.WARNING_MESSAGE);
        }
    }
    public void Sama()    
    {                            
                if(tombol == "tambah")
                {        
                snilai2 = fLayar.getText();
                Float hasil = Float.parseFloat(snilai1) + Float.parseFloat(snilai2);
                String shasil = ""+hasil;
                fLayar.setText(shasil);
                isiLayar = ("");
                }          
                if(tombol == "kurang")
                {    
                snilai2 = fLayar.getText();
                Float hasil = Float.parseFloat(snilai1) - Float.parseFloat(snilai2);
                String shasil = ""+hasil;
                fLayar.setText(shasil);
                isiLayar = ("");
                }              
                if(tombol == "kali")
                {    
                snilai2 = fLayar.getText();
                Float hasil = Float.parseFloat(snilai1) * Float.parseFloat(snilai2);
                String shasil = ""+hasil;
                fLayar.setText(shasil);
                isiLayar = ("");
                }
                
                if(tombol == "bagi")
                {                    
                snilai2 = fLayar.getText();
                Float hasil = Float.parseFloat(snilai1) / Float.parseFloat(snilai2);
                String shasil = ""+hasil;
                fLayar.setText(shasil);
                isiLayar = ("");
                }                                 
                if(tombol == "pangkat")
                {                    
                Double snilai1= Double.valueOf(fLayar.getText());
                Double snilai2=Double.valueOf(fLayar.getText());
                Double hasil=Double.valueOf(Math.pow(snilai1, snilai2));
                String shasil = ""+hasil;
                fLayar.setText(shasil);
                isiLayar = ("");
                }                                                               
    }
    
    public void On()
    {
        isiLayar="";
        fLayar.setText("0");            
    }            
    private void tampil() 
    { 
        try 
        { 
        	
        }
        catch (Exception e)
        {
            JOptionPane.showMessageDialog(this, "Ada Kesalahan!!!");
            
        }
    }              
    // Fungsi untuk mengkosongkan Objek masukan 
    void Kosong () 
        {
         fLayar.setText ("");
         fLayar.requestFocus ();
        
        }
}

