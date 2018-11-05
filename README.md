/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package chunk2methods;
import java.util.Scanner;
/**
 *
 * @author jeremy.carpenter
 */
public class PointOfSalesCalculator {
    int numHotDogs = 0;
    int numFrenchFries = 0;
    double totalSales;
    double subTotal;
    
    public static int hotDogInventory = 100;
    public static int bunInventory = 100;
    public static int orderOfFriesPerBag = 8;
    public static int bagsOfFries = 25;
    public static int totalOrdersOfFries = orderOfFriesPerBag * bagsOfFries;
    public static final double PRICE_HOTDOG = 1.50;
    public static final double PRICE_FRIES = 1.75;
    public static final double SALES_TAX = .06;
    
    
    public static void main(String[] args){
        System.out.println("How many Hot Dogs would you like?");
        Scanner myScanner = new Scanner(System.in);
        
        int numHotDogs = myScanner.nextInt();
        totalNumberOfHotdogsSold(numHotDogs);
        
        System.out.println("How many orders of French Fries would you like?");
        int numFrenchFries = myScanner.nextInt();
        totalNumberOfFrenchFriesSold(numFrenchFries);
         
        subTotalAndTaxPrices(numHotDogs, numFrenchFries);
        
        System.out.println("Thank you! Please come again!");
        
        fryAndDogInventory(numHotDogs, numFrenchFries);
        
    }//end main
    
    public static void totalNumberOfHotdogsSold(int numHotDogs){
        System.out.println("Grillin up " + numHotDogs + " hot dogs!");
        
    
    }//close hot dogs sold
    
    public static void totalNumberOfFrenchFriesSold(int numFrenchFries){
        System.out.println("Dropping " + numFrenchFries + " orders of fries!");
    }//close fries sold
    
    public static void subTotalAndTaxPrices(int numHotDogs, int numFrenchFries ){
        double totalHotDogs = PRICE_HOTDOG * numHotDogs;
        double totalFrenchFries = PRICE_FRIES * numFrenchFries;
        System.out.println("Total for Hotdogs:      $" + totalHotDogs);
        System.out.println("Total for French Fries: $" + totalFrenchFries);
        double subTotal = numHotDogs * PRICE_HOTDOG + numFrenchFries * PRICE_FRIES;
        double taxTotal = subTotal * SALES_TAX;
        double priceAfterTax = taxTotal + subTotal; 
        System.out.println("__________________");
        System.out.println("|SUBTOTAL: $" + subTotal + " |");
        System.out.println("|Tax:      $" + taxTotal + " |");
        System.out.println("|----------------|");
        System.out.println("|Total:    $" + priceAfterTax + "|");
        System.out.println("‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾");
        double revenue = totalHotDogs + totalFrenchFries;
        double netIncome;
    }
    
    public static void fryAndDogInventory(int numHotDogs, int numFrenchFries){
       // double totalHotDogs = PRICE_HOTDOG * numHotDogs;
       //double totalFrenchFries = PRICE_FRIES * numFrenchFries;
        int hotDogsLeft = hotDogInventory - numHotDogs ;
        int bunsLeft = hotDogsLeft;
        int friesLeft = totalOrdersOfFries - numFrenchFries;
        
        System.out.println("Total hot dogs left: " + hotDogsLeft);
        System.out.println("Total buns left: " + bunsLeft);
        System.out.println("Total orders of fries left: " + friesLeft);
        
        if (hotDogsLeft <= 30)
            System.out.println("You need to buy some more Hot Dogs!!!");
        else{
            System.out.println("Your Hot Dog inventory is all good..for now.");
        }
        if(friesLeft <= 30)
            System.out.println("You need to buy more fries!!!");
        else{
            System.out.println("Your French Fry inventory is all good..for now.");
        }
        if(bunsLeft <= 30)
            System.out.println("You need to buy more buns!!!");
        else{
            System.out.println("Your Hot Dog bun inventory is all good..for now.");
        }
    }//end inventory
    
    
    
}//close class
