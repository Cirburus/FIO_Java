import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.File;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.io.FileNotFoundException;

/****************************************
 * Use this template to do FI and O.
 ****************************************/ 
public class fio {

    BufferedReader inLine;
    BufferedWriter outLine;
    private String readFile;
    private String writeFile;
    boolean moreData;
    
    /****************************************
     * Default constructor.
     ****************************************/ 
    public fio () {
	readFile = null;
	writeFile = null;
	moreData = false;
    }// End constructor
    
    /***************************************
     * Constructor to open a given file.
     * @param name <- of the file
     ****************************************/
    public void openFile(String name){
	if (!name.equals(null)) {
	    readFile = name;
	    try {
		System.out.println("Opening...");
		File inFile = new File(readFile);
		if (!inFile.exists()){ throw new FileNotFoundException();}
		FileReader fileReader = new FileReader(inFile);
		inLine = new BufferedReader(fileReader);
		moreData = true;
		System.out.println("Finished");
	    } catch (FileNotFoundException e) {
		System.err.println("The file, " + readFile + " does not exist!\n");
	    }
	}else{
	    System.out.println("Please enter a file name");
	}
    }// End openFile
    
    /****************************************
     *Reads the next whole line of the file
     ****************************************/
    public String readLine(){
    	System.out.println("Reading...);
	String inputLine = null ;
	if (readFile.equals(null)) {
	    System.err.println("There is no file opened. Please check the file name or open the file");
	    System.exit(1);
	}
	try{
	    inputLine = inLine.readLine();
	    if (inputLine == null){ moreData = false;}
	    if (!moreData) { return "No More Data";}
	}catch (IOException error){
	    System.err.println ("An error occurred reading from file " + readFile + "!\n");
	    System.exit(1);
	}
	return inputLine;
    }// End readLine
    
    /**************************************** 
     * Opens a file and writes a single line
     * If the file does not exist...
     * This will create it.
     * @param name <- of file
     * @param line
     ****************************************/ 
    public void writeLine(String name, String line){
	writeFile = name;
	try{
	    System.out.println("Writing...");
            File outFile = new File(writeFile);
            if (!outFile.exists()){ outFile.createNewFile();}
	    FileWriter fw = new FileWriter(outFile.getAbsoluteFile());
	    outLine = new BufferedWriter(fw);
	    outLine.append(line);
	    System.out.println("Finished");
	}catch (IOException error){
	    System.err.println("An error occurred writing to file " + name + "!\n");
	} finally{
	    try{
	    outLine.close();
	    }catch(IOException e){
		System.err.println("There was a problem closing " + writeFile + "!\n");
	    }
	}
    }// End writeLine
    
    /****************************************
     * Peeks to see if there is more data
     ****************************************/
    public boolean hasMoreData() {
	return moreData;
    }// End hasMoreData
    
    /****************************************
     * Closes the open file.
     ****************************************/
    public void close() {
	try {
	    inLine.close();
	}catch (IOException e) {
	    System.err.println("There was a problem closing " + readFile + "!\n");
	}
	try{
	    outLine.close();
	}catch (IOException e){
	    System.err.println("There was a problem closing "+ writeFile + "!\n");
	}
    }// End fileClose
    
}//End Class
