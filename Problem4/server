package Problem4;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.PrintWriter;
import java.net.ServerSocket;
import java.net.Socket;

public class Server {
	private static final int PORT = 5000;

	public static void main(String[] args) throws IOException {
		ServerSocket listener = new ServerSocket(PORT);
		Socket client = listener.accept();

		//1: Send greeting message to the client
		PrintWriter out = new PrintWriter(client.getOutputStream(), true);
		out.println("Hello client! Enter name and age:");

		//4: Get data from the client
		BufferedReader in = new BufferedReader(new InputStreamReader(client.getInputStream()));	
		String clientData = in.readLine();
		
		//5: Check validity of data and send status message to the client
		if (clientData != null) {
			out.println("Your data was successfully sent to server");
			System.out.println("Client: " + clientData);
		} else {
			out.println("Unsuccessful communication");
		}
		
		listener.close();
		client.close();
	}
}
