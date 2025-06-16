import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class MouseEventViewer extends JFrame implements MouseListener, MouseMotionListener {

    private String eventText = "Move the mouse or click";

    public MouseEventViewer() {
        setTitle("Mouse Event Viewer");
        setSize(600, 400);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        addMouseListener(this);
        addMouseMotionListener(this);
        setVisible(true);
    }

    public void paint(Graphics g) {
        super.paint(g);
        g.setFont(new Font("Arial", Font.BOLD, 24));
        FontMetrics fm = g.getFontMetrics();
        int x = (getWidth() - fm.stringWidth(eventText)) / 2;
        int y = getHeight() / 2;
        g.drawString(eventText, x, y);
    }

    @Override
    public void mouseClicked(MouseEvent e) {
        eventText = "Mouse Clicked";
        repaint();
    }

    @Override
    public void mousePressed(MouseEvent e) {
        eventText = "Mouse Pressed";
        repaint();
    }

    @Override
    public void mouseReleased(MouseEvent e) {
        eventText = "Mouse Released";
        repaint();
    }

    @Override
    public void mouseEntered(MouseEvent e) {
        eventText = "Mouse Entered";
        repaint();
    }

    @Override
    public void mouseExited(MouseEvent e) {
        eventText = "Mouse Exited";
        repaint();
    }

    @Override
    public void mouseDragged(MouseEvent e) {
        eventText = "Mouse Dragging";
        repaint();
    }

    @Override
    public void mouseMoved(MouseEvent e) {
        eventText = "Mouse Moving";
        repaint();
    }

    public static void main(String[] args) {
        new MouseEventViewer();
    }
}