public class Pet {
			private String name;
			private String ownerName;
			private String color;
			protected Integer sex;
			public static final int MALE = 3;
			public static final int FEMALE = 2;
			public static final int SPARYED = 1;
			
			
			
			Pet(String name, String ownerName, String color){
				this.name = name;
				this.ownerName = ownerName;
				this.color = color;
			}
			String getPetName(){
				return name;
			}
			String getOwnerName(){
				return ownerName;
			}
			String getColor(){
				return color;
			}
			void setSex(int sexid){
				sex = sexid;
				
			}
			String getSex(){
				if(sex == 3) return "MALE"; 
				if(sex == 2) return "FEMALE"; 
				if(sex == 1) return "SPARYED"; 
				 
				return "invalid input";
				
			}
			public String toString(){
				String s = "";
				s += this.getPetName() + " owned by " + this.getOwnerName() + "\n"; 
				s += "Color: " + this.getColor() + "\n"; 
				s += "Sex: " + this.getSex() + "\n";
				return s;
			}
		
			
			
	}
package Boardable;

public interface Boardable {
			 
void setBoardStart(int month, int day, int year); 
void setBoardEnd(int month, int day, int year); 
boolean boarding(int month, int day, int year); 
}


public class Dog extends Pet implements Boardable
{
			private String size;
			private Date boardstart;
			private Date boardend;
			
			Dog(String name, String ownerName, String color, String size){
				
			this.size = size;
				
			}
			String getSize(){
				return size;
			}
			public String toString() {
				String s = "";
				s += this.getPetName() + " owned by " + this.getOwnerName() + "\n"; 
				s += "Color: " + this.getColor() + "\n"; 
				
				s += "Size: " + this.getSize();
				s += "Sex: " + this.getSex() + "\n";
		return s;
			}
			public void setBoardStart(int month, int day, int year){
				boardstart = new Date();
			}
			
			public void setBoardEnd(int month, int day, int year){
				boardend = new Date();
			}
			
      
      
	public class AnimalHospital {
		private List<Pet> anilist = new ArrayList<>();
		
		void printPetInfoByName(String name){
			for(Pet pet : anilist){
				if(pet.getPetName().equals(name)){
					System.out.println(pet.toString());
				}
			}
		}
		
		void printPetInfoByOwner(String name){
			for(Pet pet : anilist){
				if(pet.getOwnerName().equals(name)){
					System.out.println(pet.toString());
				}
			}
		}
		
