package authenticationsystem;
import java.util.Scanner;
import java.security.MessageDigest;

/**
 * Program allows employees to securely enter username and password to gain
 * access to the zoo's computer system. Each user will only have access to 
 * information pertaining to their specific role.
 * @author tobia
 */


public class AuthenticationSystem {
    public static void main(String[] args) {
        Scanner scnr = new Scanner(System.in);
        String username = "";
        String originalPassword = "";
        String hashedPassword = "";
        int i = 1;
        
        for (i = 1; i <= 3; ++i){
            
            System.out.println("Username: "); //prompt user to enter their username
            username = scnr.nextLine();
        
            System.out.println("Password: "); //prompt user to enter theit password
            originalPassword = scnr.nextLine();
        
            if (username.equals("bruce.grizzlybear") && originalPassword.equals("letmein")) { //username needs a specific password
                System.out.print("Welcome Admin User!"); //just a placeholder. should redirect the user to their view of the site
            }
            if (username.equals("rasario.dawson") && originalPassword.equals("animal doctor")) {
                System.out.print("Welcome Admin User!");
            }
            if (username.equals("bernie.gorilla") && originalPassword.equals("secret password")) {
                System.out.print("Welcome Vet!");
            }
            if (username.equals("jerome.grizzlybear") && originalPassword.equals("grizzly1234")) {
                System.out.print("Welcome Vet");
            }
            if (username.equals("donald.monkey") && originalPassword.equals("M0nk3y business")) {
                System.out.print("Welcome Zookeeper!");
            }
            if (username.equals("griffin.keyes") && originalPassword.equals("alphabet soup")) {
                System.out.print("Welcome Zookeeper!");
            }
            else {
                System.out.println("Invalid credentials. You will be locked out after 3 failed attempts.");
            }
        }
    }
    
}


import java.security.MessageDigest;

public class MD5Digest {

	public static void main(String[] args) throws Exception {
      
      //Copy and paste this section of code
		String original = "letmein";  //Replace "password" with the actual password inputted by the user
		MessageDigest md = MessageDigest.getInstance("MD5");
		md.update(original.getBytes());
		byte[] digest = md.digest();
                StringBuffer sb = new StringBuffer();
		for (byte b : digest) {
			sb.append(String.format("%02x", b & 0xff));
		}
      //End copy/paste

		System.out.println("original:" + original);
		System.out.println("digested:" + sb.toString()); //sb.toString() is what you'll need to compare password strings
	}

}
