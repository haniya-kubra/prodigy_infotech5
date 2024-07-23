import java.io.FileWriter;
import java.io.IOException;

public class ProductScraper {

    public static void main(String[] args) {
        // Simulated product data
        String[][] products = {
                {"Product 1", "Rs. 1000", "4.5"},
                {"Product 2", "Rs. 5250", "4.2"},
                {"Product 3", "Rs. 6000", "4.8"}
        };

        String outputFilePath = "products.csv"; // Output CSV file path

        try {
            writeCSV(outputFilePath, products);
            System.out.println("Product information extracted and saved to " + outputFilePath);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

    private static void writeCSV(String filename, String[][] products) throws IOException {
        FileWriter writer = new FileWriter(filename);
        writer.write("Name,Price,Rating\n");

        for (String[] product : products) {
            writer.write(String.join(",", product) + "\n");
        }

        writer.close();
    }
}
