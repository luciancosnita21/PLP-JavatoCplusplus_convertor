Convertor din Java in C++


     Scopul acestui proiect este crearea unei aplicatii capabile sa faca tranzitia intre doua limbaje de programare,
in cazul nostru Java si C++.
     Pentru a defini mai bine caracteristicile acestei aplicatii o vom imparti  in 3 module:
   1.parsarea:-se ia codul scris in Java dintr-un fisier si se pune intr-un sir de caractere fara aliniate(se presupune
ca codul scris in java este corect)
              -are loc crearea unui arbore de structuri:clase-functii-declaratii. De exemplu:
                       class clasa
                      {   
	                string stare;
	                vector<functie> functii;
	                vector<clasa> relatii;
	                string continut;
                      public:
	                string echivalent_class();
                       }
        
   2.generare structuri echivalente:pentru fiecare structura scrisa in java  se cauta un echivalent in C++;
         
   3.converisia:pe baza structurilor alcatuite se vor genera clasele echivalente in C++;

   Limbajul de programare in care va fi creat proiectul este C++.
   Precizam ca nu toate structurile din java vor putea fi convertite prin ajutorul aplicatiei; o lista cu ce este permis si ce nu 
este permis va fi creata pe parcursul dezvoltarii proiectului.

  Exemplu:
Fie urmatorul cod scris in java:

public class Person {
 private  ArrayList<String> tool = new ArrayList<>();
 private int id;
 protected String name;
 public Person() { }
 public Person(String name) {
 this.name = name;
 }
 public String getName() {
 return name;
 }
 void setName(String name) {
 this.name = name;
 }
 public void AddTool(String t)
 {   
     this.tool.add(t);
     
 }
public void PrintTool()
{ for ( int j=0; j<tool.size(); j++ )
      System.out.println(this.tool.get(j) );
}
}
       

Prin intermediul aplicatiei noastre vom genera:


class Person
{private :
	int id;
	vector<string> tool;
protected:
	string name;
public:
	Person() {};
	Person(string name)
	{
		this->name = name;
	}
	string getname()
	{  
		return name;
	}
	void setName(string name)
	{
		this->name = name;
	}
	void AddTool(string c) {
		tool.push_back(c);
	}
	void PrintTool() {
		vector<string>::iterator it;

		for (it = tool.begin(); it != tool.end(); it++)
		{
			for (int i = 0; i < (*it).length(); i++) {
				cout << (*it)[i];
			}
			cout << endl;
		}
	}
};
