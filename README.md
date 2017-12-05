package butelka;

public class Butelka {
    private double ileLitrow;
    
    
    Butelka(double ileLitrow)
    {
        this.ileLitrow = ileLitrow;
    }
    
    double getIleLitrow()
    {
        return ileLitrow;
    }
    void wlej (double ilosc) 
    {
        this.ileLitrow += ilosc;
    }
    boolean wylej (double ilosc)
    {
        if (ilosc < ileLitrow)
            this.ileLitrow -= ilosc;
        else
            return false;
        
        return true;
    }
    
    void przelej(double ilosc, Butelka gdziePrzelac)
    {
        if (this.wylej (ilosc))
        {
            gdziePrzelac.wlej(ilosc);
        }
        else 
            System.out.println("Za mało");
                    
    }
            

 
    public static void main(String[] args) {
        Butelka[] butelka = new Butelka[50];
        
       
        int i = 0;      
        int y = 0;
        
        while ( i < 50)
        {
            butelka[i] = new Butelka(y);
            
            i++;
            
            y++;
            
        }
                         
        butelka[30].przelej (28, butelka[47]);
        
        
        
        System.out.println(butelka[30].getIleLitrow());
        System.out.println(butelka[47].getIleLitrow());
       
    }   
    
}
