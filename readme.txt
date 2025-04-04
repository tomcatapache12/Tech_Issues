import java.awt.*;
import java.util.concurrent.TimeUnit;

public class KeepAlive {
    public static void main(String[] args) {
        try {
            Robot robot = new Robot();
            long end = System.currentTimeMillis() + TimeUnit.HOURS.toMillis(3);

            while (System.currentTimeMillis() < end) {
                // Move mouse slightly to simulate activity
                Point location = MouseInfo.getPointerInfo().getLocation();
                int x = location.x;
                int y = location.y;

                robot.mouseMove(x + 1, y);
                Thread.sleep(500);
                robot.mouseMove(x - 1, y);

                // Wait for 60 seconds before next activity
                Thread.sleep(60_000);
            }

            System.out.println("Done keeping session alive for 3 hours.");
        } catch (AWTException | InterruptedException e) {
            e.printStackTrace();
        }
    }
}
