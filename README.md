# Future Women in STEM
<img width="1536" height="1024" alt="Preview Image Github Women STEM" src="https://github.com/user-attachments/assets/823d1eeb-433f-4819-87a5-1808c7520dd4" />


Future Women in STEM is a Java program designed to encourage and support girls and women interested in STEM fields. 
The program provides educational resources, mentorship opportunites, details inspirational woman figures in computer science, and tools that help users explore STEM career paths and financial opportunites.

Problem:
Women in STEM remain underrepresented in many STEM fields, especially computer science and other technology related careers.
Many students may not know where to find:

- mentor opportunities
- coding communities
- scholarships and financial support
- women role models in STEM/technology

Solution:
Future Women in STEM program assists users with the following:

- learn about influencual women in technology and computer science fields
- discover organizations that support girls and women in coding
- explore mentorship opportunites
- take a short STEM career quiz
- estimate potential scholarhip funding

The goal is to create a resource hub that promotes these solutions and opportunities for girls and women interested in STEM.

Raw Program:

package womenInStem;

import java.util.ArrayList;
import java.util.Scanner;

public class futureWomenInStem {

   public static void main(String[] args) {
      Scanner scanner = new Scanner(System.in);

      ArrayList<String> resources = new ArrayList<String>();

      // Resource list for girls/women in STEM
      resources.add("Women Who Code");
      resources.add("Girls Who Code");
      resources.add("Society Of Women In STEM");
      resources.add("NCWIT: National Center for Women and IT");

      ArrayList<String> mentorshipGroups = new ArrayList<String>();

      // Mentorship groups in STEM
      mentorshipGroups.add("Women in Web Development");
      mentorshipGroups.add("Beginners in Coding");
      mentorshipGroups.add("TechWomen for Emerging International Leaders");
      mentorshipGroups.add("Society of Women Engineers (SWE) Mentor Network");

      boolean running = true;

      while (running) {
         System.out.println("\n-=-=-=-=- Future Women In STEM -=-=-=-=-");
         System.out.println("1. Learn about influencers in the computer science world");
         System.out.println("2. Coding resources");
         System.out.println("3. Mentorship groups available");
         System.out.println("4. STEM career quiz");
         System.out.println("5. Scholarship calculator");
         System.out.println("6. Exit the program");

         System.out.print("Enter your choice: ");
         int choice = scanner.nextInt();

         switch (choice) {
            case 1:
               learnInfluencers(scanner);
               break;

            case 2:
               showResources(resources);
               break;

            case 3:
               joinMentorship(scanner, mentorshipGroups);
               break;

            case 4:
               careerQuiz(scanner);
               break;

            case 5:
               scholarshipCalculator(scanner);
               break;

            case 6:
               System.out.println("Thank you for using Future Women In STEM!");
               running = false;
               break;

            default:
               System.out.println("Invalid choice. Please try again.");
         }
      }

      scanner.close();
   }

   // Feature 1: Influencers and historical figures
   public static void learnInfluencers(Scanner scanner) {
      System.out.println("\n-=-=-=-=- Learn About Popular Influencers in Computer Science -=-=-=-=-");
      System.out.println("1. Grace Hopper");
      System.out.println("2. Katherine Johnson");
      System.out.println("3. Radia Perlman");

      System.out.print("Enter your choice: ");
      int choice = scanner.nextInt();

      switch (choice) {
         case 1:
            System.out.println("\nGrace Hopper:");
            System.out.println("Grace Hopper was a computer scientist who developed early computer languages, including COBOL, and was a pioneer in programming.");
            break;

         case 2:
            System.out.println("\nKatherine Johnson:");
            System.out.println("Katherine Johnson was a mathematician who calculated critical trajectories for NASA's Space Race and Apollo 11 moon missions.");
            break;

         case 3:
            System.out.println("\nRadia Perlman:");
            System.out.println("Radia Perlman is a computer scientist known as the 'Mother of the Internet'. She developed the algorithm behind the Spanning Tree Protocol (STP).");
            break;

         default:
            System.out.println("Invalid choice. Please try again.");
      }
   }

   // Feature 2: Resources
   public static void showResources(ArrayList<String> resources) {
      System.out.println("\n--- Women in Coding Resources ---");

      for (int i = 0; i < resources.size(); i++) {
         System.out.println((i + 1) + ". " + resources.get(i));
      }
   }

   // Feature 3: Joining a mentorship group
   public static void joinMentorship(Scanner scanner, ArrayList<String> groups) {
      System.out.println("\n-=-=-=-=- Mentorship Groups -=-=-=-=-");

      for (int i = 0; i < groups.size(); i++) {
         System.out.println((i + 1) + ". " + groups.get(i));
      }

      System.out.print("Enter the number of the group you want to join: ");
      int choice = scanner.nextInt();

      if (choice >= 1 && choice <= groups.size()) {
         System.out.println("You joined: " + groups.get(choice - 1));
      }
      else {
         System.out.println("Invalid group selection.");
      }
   }

   // Feature 4: STEM career quiz
   public static void careerQuiz(Scanner scanner) {
      System.out.println("\n-=-=-=-=- STEM Career Quiz -=-=-=-=-");

      int score = 0;

      System.out.println("1. Do you enjoy solving logical problems?");
      System.out.println("1 = Yes   2 = No");
      int q1 = scanner.nextInt();
      if (q1 == 1) {
         score++;
      }

      System.out.println("2. Do you like building or creating technology?");
      System.out.println("1 = Yes   2 = No");
      int q2 = scanner.nextInt();
      if (q2 == 1) {
         score++;
      }

      System.out.println("3. Do you like analyzing data or patterns?");
      System.out.println("1 = Yes   2 = No");
      int q3 = scanner.nextInt();
      if (q3 == 1) {
         score++;
      }

      System.out.println("\n-=-=-=-=- Quiz Result -=-=-=-=-");

      if (score == 3) {
         System.out.println("You may enjoy Software Engineering or Data Science!");
      }
      else if (score == 2) {
         System.out.println("You may enjoy Cybersecurity or Web Development!");
      }
      else {
         System.out.println("You may enjoy Project Management!");
      }
   }

   // Feature 5: Scholarship calculator
   public static void scholarshipCalculator(Scanner scanner) {
      System.out.println("\n-=-=-=-=- Scholarship Calculator -=-=-=-=-");

      System.out.print("How many scholarships did you apply for? ");
      int scholarships = scanner.nextInt();

      System.out.print("Average scholarship amount ($): ");
      double amount = scanner.nextDouble();

      double total = scholarships * amount;

      System.out.println("Estimated total scholarship funding: $" + total);
   }
}
