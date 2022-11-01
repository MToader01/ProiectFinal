// clasa Animal
package Animal;

public class Animal{
    private String nume;

    private String specie;

    private String rasa;
    private int varsta;

    public Animal()
    {}

    public Animal(String nume, String specie, String rasa, int varsta)
    {
        this.nume=nume;
        this.specie=specie;
        this.rasa=rasa;
        this.varsta=varsta;
    }

    public void setNume(String nume){
        this.nume=nume;
    }

    public void setSpecie(String specie){
        this.specie=specie;
    }

    public void setRasa(String rasa){
        this.rasa=rasa;
    }

    public void setVarsta(int varsta){
        this.varsta=varsta;
    }

    public String getNume(){
        return this.nume;
    }

    public String getSpecie(){
        return this.specie;
    }

    public String getRasa(){
        return this.rasa;
    }

    public int getVarsta(){
        return this.varsta;
    }
}



//clasa Client
package Client;

public class Client{
    private String nume;

    private String telefon;

    private String adresa;

    public Client()
    {}

    public Client(String nume, String telefon, String adresa)
    {
        this.nume=nume;
        this.telefon=telefon;
        this.adresa=adresa;
    }

    public void setNume(String nume){
        this.nume=nume;
    }

    public void setTelefon(String telefon){
        this.telefon=telefon;
    }

    public void setAdresa(String adresa){
        this.adresa=adresa;
    }


    public String getNume(){
        return this.nume;
    }

    public String getTelefon(){
        return this.telefon;
    }

    public String getAdresa(){
        return this.adresa;
    }
}




//AdaugareAnimal
import Animal.Animal;
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
public class AdaugareAnimal {
    private static AdaugareAnimal Instance = new AdaugareAnimal();
    private JPanel Panel;
    private JLabel Message;
    private JTextField NameText;
    private JLabel NameLabel;
    private JButton Insert;
    private JTextField SecondNameText;
    private JTextField AgeText;
    private JTextField SalaryText;
    private JLabel SecondName;
    private JLabel Age;
    private JLabel Salary;



    private AdaugareAnimal() {
        Insert.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                Animal animal = new Animal();
                animal.setNume(NameText.getText());
                animal.setSpecie(NameText.getText());
                animal.setRasa(NameText.getText());
                animal.setVarsta(Integer.parseInt(AgeText.getText()));
                AdapostAnimale.getInstance().AddAnimal(animal);
                AdapostAnimale.getInstance().getFrameAdaugareAnimal().setVisible(false);
                AdapostAnimale.getInstance().getFrame().setVisible(true);
            }
        });
    }

    public static AdaugareAnimal getInstance(){
        return Instance;
    }

    public JPanel getPanel(){
        return Panel;
    }
}




//AdaugareClient
import Client.Client;
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
public class AdaugareClient {
    private static AdaugareClient Instance = new AdaugareClient();
    private JPanel Panel;
    private JLabel Message;
    private JTextField NameText;
    private JLabel NameLabel;
    private JButton Insert;
    private JTextField SecondNameText;
    private JTextField AgeText;
    private JTextField SalaryText;
    private JLabel SecondName;
    private JLabel Age;
    private JLabel Salary;



    private AdaugareClient() {
        Insert.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                Client client = new Client();
                client.setNume(NameText.getText());
                client.setTelefon(NameText.getText());
                client.setAdresa(NameText.getText());
                AdapostAnimale.getInstance().AddClient(client);
                AdapostAnimale.getInstance().getFrameAdaugareC().setVisible(false);
                AdapostAnimale.getInstance().getFrame().setVisible(true);
            }
        });
    }

    public static AdaugareClient getInstance(){
        return Instance;
    }

    public JPanel getPanel(){
        return Panel;
    }
}
