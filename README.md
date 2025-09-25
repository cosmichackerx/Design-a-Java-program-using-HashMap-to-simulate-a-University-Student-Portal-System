# Design-a-Java-program-using-HashMap-to-simulate-a-University-Student-Portal-System
```java
import java.util.HashMap;
import java.util.Map;
import java.util.LinkedHashMap;
import java.util.TreeMap;

/**
 * A Java program to simulate a University Student Portal System
 * using various Map implementations.
 */
public class StudentPortal {

    public static void main(String[] args) {

        System.out.println("--- University Student Portal System (HashMap) ---");

        // Use the 'var' keyword for type inference.
        // HashMap does not guarantee any order.
        var studentData = new HashMap<Integer, String>();

        // 1. Add Items: Insert at least 5 students.
        System.out.println("\n1. Adding Students to the System...");
        studentData.put(101, "Alice Johnson");
        studentData.put(105, "Bob Williams");
        studentData.put(102, "Charlie Brown");
        studentData.put(104, "Diana Miller");
        studentData.put(103, "Ethan Davis");
        System.out.println("Current students: " + studentData);

        // 2. Access an Item: Retrieve and display a student's name by roll number.
        System.out.println("\n2. Accessing a Student's Name (Roll No. 102):");
        String studentName = studentData.get(102);
        System.out.println("Student with roll number 102 is: " + studentName);

        // 3. Remove an Item: Remove a student by roll number.
        System.out.println("\n3. Removing a Graduated Student (Roll No. 105)...");
        studentData.remove(105);
        System.out.println("Updated student list after removal: " + studentData);

        // 4. HashMap Size: Display how many students are currently enrolled.
        System.out.println("\n4. Current Student Count:");
        System.out.println("There are " + studentData.size() + " students currently enrolled.");

        // 5. Loop Through a HashMap:
        System.out.println("\n5. Looping Through the HashMap...");

        // 5a. Print all roll numbers (keys).
        System.out.println("\n- All Roll Numbers (Keys):");
        for (Integer rollNumber : studentData.keySet()) {
            System.out.println(rollNumber);
        }

        // 5b. Print all student names (values).
        System.out.println("\n- All Student Names (Values):");
        for (String name : studentData.values()) {
            System.out.println(name);
        }

        // 5c. Print both roll numbers and names together (entries).
        System.out.println("\n- All Student Entries (Roll No. & Name):");
        for (Map.Entry<Integer, String> entry : studentData.entrySet()) {
            System.out.println("Roll No: " + entry.getKey() + ", Name: " + entry.getValue());
        }

        // 6. The Map Interface: Demonstrate usage of various methods.
        System.out.println("\n6. Using Map Interface Methods...");
        System.out.println("- Checking if roll number 101 exists: " + studentData.containsKey(101));
        System.out.println("- Checking if 'Charlie Brown' exists as a value: " + studentData.containsValue("Charlie Brown"));
        
        System.out.println("- Replacing a student's name (Roll No. 104):");
        studentData.replace(104, "Diana Miller", "Diana Miller-Smith");
        System.out.println("Updated student list: " + studentData);

        // 7. Simulating Other Map Types
        System.out.println("\n--- Simulating LinkedHashMap and TreeMap ---");

        // LinkedHashMap: Preserves insertion order.
        System.out.println("\n7a. Using LinkedHashMap (Preserves Insertion Order):");
        var linkedStudentData = new LinkedHashMap<Integer, String>();
        linkedStudentData.put(101, "Alice Johnson");
        linkedStudentData.put(105, "Bob Williams"); // This order is preserved
        linkedStudentData.put(102, "Charlie Brown");
        linkedStudentData.put(104, "Diana Miller");
        System.out.println("LinkedHashMap maintains the order of insertion:");
        for (Map.Entry<Integer, String> entry : linkedStudentData.entrySet()) {
            System.out.println(entry.getKey() + " -> " + entry.getValue());
        }

        // TreeMap: Automatically sorts keys in natural order.
        System.out.println("\n7b. Using TreeMap (Automatically Sorts by Roll Number):");
        var treeStudentData = new TreeMap<Integer, String>();
        treeStudentData.put(101, "Alice Johnson");
        treeStudentData.put(105, "Bob Williams"); // This will be placed after 104
        treeStudentData.put(102, "Charlie Brown");
        treeStudentData.put(104, "Diana Miller");
        System.out.println("TreeMap automatically sorts students by roll number:");
        for (Map.Entry<Integer, String> entry : treeStudentData.entrySet()) {
            System.out.println(entry.getKey() + " -> " + entry.getValue());
        }

        // 8. When Order Matters: Why choose LinkedHashMap or TreeMap?
        System.out.println("\n8. Why LinkedHashMap or TreeMap Might Be Chosen:");
        System.out.println("- LinkedHashMap: Useful for a 'Recently Added' section or to display a list of students in the exact order they were enrolled. The predictable order is crucial for presenting data chronologically.");
        System.out.println("- TreeMap: Ideal for systems where you need students to be automatically sorted by roll number (e.g., in a faculty report, a directory, or for quick lookups by ordered range). The sorting is done automatically and efficiently.");
    }
}
```
