import java.awt.Image;
import java.awt.Toolkit;
import java.awt.image.PixelGrabber;
 
public class Compare {
static void processImage() {
 
String file1 = "https://presentationpictures.files.wordpress.com/2010/07/green-fresh-plant-growing.jpg";

//delete and paste new image link image link to be compared inside the inverted comma

String file2 = "https://presentationpictures.files.wordpress.com/2010/07/green-fresh-plant-growing.jpg";

//delete and paste new  image link to be compare inside the inverted comma 

Image image1 = Toolkit.getDefaultToolkit().getImage(file1);
Image image2 = Toolkit.getDefaultToolkit().getImage(file2);
 
try {
PixelGrabber grab1 =new PixelGrabber(image1, 0, 0, -1, -1, false);
PixelGrabber grab2 =new PixelGrabber(image2, 0, 0, -1, -1, false);
 
int[] data1 = null;
 
if (grab1.grabPixels()) {
int width = grab1.getWidth();
int height = grab1.getHeight();
data1 = new int[width * height];
data1 = (int[]) grab1.getPixels();
}
 
int[] data2 = null;
 
if (grab2.grabPixels()) {
int width = grab2.getWidth();
int height = grab2.getHeight();
data2 = new int[width * height];
data2 = (int[]) grab2.getPixels();
}
 
System.out.println("Images are same: " + java.util.Arrays.equals(data1, data2));
 
} catch (InterruptedException e1) {
e1.printStackTrace();
}
}
 
public static void main(String args[]) {
processImage();
}
}
