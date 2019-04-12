### Ceva ce trebuia facut

Operatori: matematici, logici si de comparatie ce returneaza bolean
Structura de control
* conditional
  * swich
  * if else
* repetitiv

Nume clasa nu incep cu cifra, spatiu, caractere speciale   

super()
hiding fields
imutabilitate
encapsulare

Cerc isA Punct
Cerc2d hasA Punct2d (cercul are ca atribut Punct) trebuie sa ii faci tu constructorul de la punct->cerc->cilindru

Suprascriere @Overwrite

abstract(clasele abstr pot avea constructori dar nu pot fi instantiate)
## Cursul_5
polimorfism   
interface   
enum  
tipuri imbricate   
tipuri anonime   

## Cursul_6
lambda   
annotation   
design patterns  ---> singleton pattern, factory, builder, decorator, kiss   

## Cursul_7
### erori
 * clasa Throwable  
    * mostenit de Error  
    * mostenit de Exception (s.n. checked)  
     ** mostentit de RuntimeException (s.n. unchecked / runtime)  
### exceptii  
 * de sistem
   * FileNotFoundException
   * NullPointerException
   * ArrayOutOfBoundException array v[6] desi ele sunt 5
   * IOException
 * de aplicatii(business)  
   * la bancomat cand nu ai bani
   * campuri de new user necompletate 

!!!  final(int x, obj, metoda, clasa) finally(try si AutoCloseable) finalize(garbage collector)

## Cursul_8
Clasele rapper
* Byte
* Short
* Integer
* Long
* Double
* Floate
* Character
* Boolean  

Integer i = Integer.parseInt("123");  

Tipurile generice   public class Cutie<T>   numai de tip Object, accepta array
```
public class Exemplul1{
    public static void main(String []args){
        Cutie c1 = new Cutie(); //backwards compatibility
        
        Carte cr1 = new Carte("Morometii", 300);
        Creion cre1 = new Creion("rosu", 5);
        
        Cutie<Carte> c2;
        c2 = new Cutie<Carte>();
        Cutie<Creion> c3 = new Cutie<Creion>(5, new Creion("albastru", 10));
        Cutie<Integer> c4 = new Cutie<>();
        System.out.println(c3.continut);
        
        Cutie<int[]> c6 = new Cutie<>();
        
        Cutie<?> c7; //polimorfism ?= Object
        c7 = new Cutie<Carte>();
        c7 = new Cutie<Creion>();
        c7 = new Cutie<Integer>();
        
        Cutie<? extends Number> c8;
        c8 = new Cutie<Double>();
        c8 = new Cutie<Integer>();
        //c8 = new Cutie<String>(); 
        
        Cutie<? super Integer> c9;
        c9 = new Cutie<Number>();
        c9 = new Cutie<Object>();
        //c9 = new Cutie<Creion>();
    }
}
```
```
public class Cutie<T>{
    double volum;
    T continut;
    
    Cutie(){}
    
    Cutie(double volum, T continut){
        this.volum=volum;
        this.continut = continut;
    }
    
    public T getContinut(){
        return this.continut;
    }
}
```
```
public class Carte{
    String titlu;
    int nrPag;
    
    Carte(String titlu, int nrPag){
        this.titlu = titlu;
        this.nrPag = nrPag;
    }
    
    @Override
    public String toString(){
        return "Carte" + this.titlu + " " + this.nrPag; 
    }
}

```
```
public class Creion{
    String culoare;
    int pret;
    
    Creion(String culoare, int pret){
        this.culoare = culoare;
        this.pret = pret;
    }
    
    @Override
    public String toString(){
        return "Creion"+ culoare+" "+pret;
    }
}
```


