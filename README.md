# 100LINES_CRUD

import java.util.*;

class Student implements Comparable<Student>{  

    int rollno;  
    
    String name;  
    
    int age;  
    
    Student(int rollno,String name,int age){  
    
    this.rollno=rollno;  
    
    this.name=name;  
    
    this.age=age;  
    
    }  
      
    public int compareTo(Student st){  
    
    if(age==st.age)  
    
    return 0;  
    
    else if(age>st.age)  
    
    return 1;  
    
    else  
    
    return -1;  
    
    }

    public int length() {
    
        return 0;
        
    }

    public boolean contains(String delete) {
    
        return false;
        
    }  
    
}  

public class Main{  

    public static void main(String args[]){  
    
    ArrayList<Student> al=new ArrayList<Student>(); 
    
    ArrayList<Student> newArray=new ArrayList<Student>();   
    
    al.add(new Student(101,"Vijay",23));  
    
    al.add(new Student(106,"Ajay",27));  
    
    al.add(new Student(105,"Jai",21));  
    
    // Add
    Scanner userinput = new Scanner(System.in);
    
    System.out.println("What You Want to Insert");
    
    try{
    
        String Name= userinput.next();
        
        al.add(new Student(109,Name,33));
        
    }catch(Exception e){
    
        System.out.println(e);
        
    }
    
    Collections.sort(al); 
    
    // Display 
    
    for(Student st:al){
    
        System.out.println(st.rollno+" "+st.name+" "+st.age);  
        
    }  
    
    // Search
    
    System.out.println("What you want to find?");
    
    String SearchName = userinput.next();

    for(Student st:al){  
    
        if(SearchName.contains(st.name)){
        
            System.out.println(st.rollno+" "+st.name+" "+st.age);  
            
        }
        
    }  
    
    // Delete
    
    //Iterator<Student> itr = al.iterator();
    
    System.out.println("What you want to delete?");
    
    String Delete = userinput.next();
    
    for(Student st:al){  
    
        if(!Delete.contains(st.name)){
        
            newArray.add(new Student(st.rollno,st.name,st.age));
            
        }
        
    }  
    System.out.println("Display Again");
    
    for(Student st:newArray){  
    
        System.out.println(st.rollno+" "+st.name+" "+st.age);  
        
    } 
    
    // Clone Back 
    
    System.out.println("Original");
    
    al = newArray;
    
    for(Student st:al){  
    
        System.out.println(st.rollno+" "+st.name+" "+st.age);  
        
    } 
    
    // Last Task
    
    System.out.println("______________________________________s");
    
    System.out.println("Modified");
    
    System.out.println("Which Row You Want To Modify");
    
    String rows = userinput.next();
    
    System.out.println("Which Column You Want To Modify");
    
    String columns = userinput.next();
    
    System.out.println("What you want to edit");
    
    String modified = userinput.next();
    
    System.out.println("Output...");
    
    int rows_integer = Integer.parseInt(rows);
    
    int index = 0;
    
    for(Student st:al){  
    
        if(rows_integer == index){
        
            al.set(index,new Student(3,modified,9));
            
        }
        
        index++;
        
    }  
    
    System.out.println("After edited");
    
    for(Student st:al){  
    
        System.out.println(st.rollno+" "+st.name+" "+st.age);
        
    } 
    
   
   }  
   
} 
