# Use-Monte-Carlo-simulation-to-estimate-the-value-of-the-mathematical-constant-e
This Java code estimates the value of π (PI) using the Monte Carlo method by generating a specified number of random points within a unit square and calculating the ratio of points that fall within an inscribed unit circle to the total number of points. The estimated value

import java.util.Random;
import java.util.Scanner;

public class MonteCarloPI {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the number of random points to generate  ");
        
        
        int N = scanner.nextInt();

        //This line initializes a variable insideCircle to count the number of random points that fall within the inscribed circle.
        int insideCircle = 0;
        //his line creates a Random object named rand to generate random numbers
        Random rand = new Random();

        //This line starts a for loop that will generate N random points
        for (int i = 0; i < N; i++)
         {

            //Inside the loop, this line generates a random number x between 0 and 1 using rand.nextDouble()
            double x = rand.nextDouble(); // Random x-coordinate between 0 and 1

            
            double y = rand.nextDouble(); // Random y-coordinate between 0 and 1

            //This line calculates the squared distance from the origin for the generated point using the Pythagoras theroem
            double distance = x * x + y * y; // Distance from the origin (squared)

            //if yhe random point multilied togther added up is under 1 then its countef if it not then its counted
            //his line checks if the squared distance is less than or equal to 1, which means the point in the circle
            if (distance <= 1) 
            {
                //f the point is inside the circle, this line increments the insideCircle counte
                insideCircle++;
            }
        }
        //After generating all random points and counting the ones inside the circle, this line calculates the estimated value of pi

        double estimatedPI = 4.0 * insideCircle / N;
        System.out.println("Estimated PI: " + estimatedPI);

        scanner.close();
    }
}
 of π is then determined by scaling this ratio by a factor of 4
