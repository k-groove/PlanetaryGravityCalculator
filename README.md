PlanetaryGravityCalculator
==========================

Given the dimensions of several planets and an object's mass, calculate how much force is applied on the object at the surface of the planet. Pretend the object is quite small for simplicity of your caluclations.
//first class
import java.text.DecimalFormat;
import java.util.Scanner;
public class PlanetaryGravityCalculator {
	private String name;
	private double radius;
	private double density;
	private double volume;
	private static double objectMass = objectMass();;
	//given value
	private double gravity = (6.67 * Math.pow(10,-11));
	//constructor for planets
	public PlanetaryGravityCalculator(String name, double radius, double density){
		super();
		this.name = name;
		this.radius = radius;
		this.density = density;
		this.volume = ((4.0/3.0)*(Math.PI)*(Math.pow(this.radius, 3.0)));
	}
	public static void main(String[]args){		
		GravityTest.main(args);
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public double getRadius() {
		return radius;
	}
	public void setRadius(double radius) {
		this.radius = radius;
	}
	public double getDensity() {
		return density;	}

	public void setDensity(double density) {
		this.density = density;	}

	public String toString() {
		DecimalFormat numberFormat = new DecimalFormat("#.000");
		return name + " " + numberFormat.format(force(this.objectMass, this.mass(this.volume, getDensity())));
	}
	//calculate mass of planet
	public double mass(double volume, double density){
		double mass = volume * density;
		return mass;
	}
	//calculates force of object and planet
	public double force (double objectMass, double planetMass){
		double force = ((gravity) * ((objectMass * planetMass)/Math.pow(radius, 2.0)));
		return force;
	}
	//asks for user input of objects mass
	public static double objectMass(){
		Scanner input = new Scanner(System.in);
		System.out.println("What is the mass of your object?");
		objectMass = input.nextDouble();
		return objectMass;
		}
}
//test class for different planets
import exceptions.InvalidRadiusException;
public class GravityTest {
	public static void main(String[]args){
	//try{	
		PlanetaryGravityCalculator mercury = new PlanetaryGravityCalculator("Mercury", 2439700, 5427);
		System.out.println(mercury);		
		PlanetaryGravityCalculator venus = new PlanetaryGravityCalculator("Venus", 6051900, 5243);
		System.out.println(venus);
		PlanetaryGravityCalculator earth = new PlanetaryGravityCalculator("Earth", 6367445, 5515);
		System.out.println(earth);		
		PlanetaryGravityCalculator mars = new PlanetaryGravityCalculator("Mars", 3386000, 3934);
		System.out.println(mars);		
		PlanetaryGravityCalculator jupiter = new PlanetaryGravityCalculator("Jupiter", 69173000, 1326);
		System.out.println(jupiter);		
		PlanetaryGravityCalculator saturn = new PlanetaryGravityCalculator("Saturn", 57316000, 687);
		System.out.println(saturn);		
		PlanetaryGravityCalculator uranus = new PlanetaryGravityCalculator("Uranus", 25266000, 1270);
		System.out.println(uranus);		
		PlanetaryGravityCalculator neptune = new PlanetaryGravityCalculator("Neptune", 24553000, 1638);
		System.out.println(neptune);		
		PlanetaryGravityCalculator pluto = new PlanetaryGravityCalculator("Pluto",1173000, 2050);
		System.out.println(pluto);
//	}
	//catch ( ex) {
	  //    System.out.println("Radius must be positive and greater than 0.");
	}
	}

