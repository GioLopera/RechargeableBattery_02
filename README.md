# RechargeableBattery_02
package battery;

/**
 * Autor:  @GioLopera
 */
public class Battery {

    private double maxCapacity;
    private double curCapacity;
    
    public Battery(double capacity)
    {
        maxCapacity = capacity;
        curCapacity = maxCapacity;
    }
    
    public void drain(double amount)
    {
        curCapacity -= amount;
    }
    
    public void charge()
    {
        curCapacity = maxCapacity;
    }
    
    public double getRemainingCapacity()
    {
        return curCapacity;
    }
    
}

// BatteryTester

package battery;

public class BatteryTester 
{
    public static void main(String[] args)
    {
        Battery battery = new Battery(100.0);
        
        System.out.println(battery.getRemainingCapacity());
        System.out.println("Expected: 100.0");
        
        battery.drain(23.4);
        battery.drain(9.7);
        
        System.out.println(battery.getRemainingCapacity());
        System.out.println("Expected: 66.9");
        
        battery.charge();
        System.out.println(battery.getRemainingCapacity());
        System.out.println("Expected: 100.0");
        
    }
    
}
