---
title: VMSS Resource Pack (v2.02.3)
date: 2023-04-04 11:00:00 -0500
categories: [School]
tags: [resources]     # TAG names should always be lowercase
---

# Epic Resources Here!

### Course Resources:
- [GitHub Repo](https://github.com/IsaacJ60/school/tree/master/Highschool/Grade%2011)

### Contests:
- [Watermoo Stuff Practice](https://www.cemc.uwaterloo.ca/contests/past_contests.html)
- [AMC](https://www.maa.org/math-competitions/amc-1012) (Rulers OP!)

### Free Student Resources:
- https://github.com/kamath/student-free-stuff

## CS Resources:

- Git Stuff: https://cs50.harvard.edu/web/2020/notes/1/
- Gr11 Pygame Template Code:

```
from pygame import *

WIDTH,HEIGHT = 800, 600
screen = display.set_mode((WIDTH, HEIGHT))
RED = (255, 0, 0)
GREY = (127, 127, 127)
BLACK = (0, 0, 0)
BLUE = (0, 0, 255)
GREEN = (0, 255, 0)
YELLOW = (255, 255, 0)

running = True

while running:
  for evt in event.get():
    if evt.type==QUIT:
      running=False

  mx,my=mouse.get_pos()
  mb=mouse.get_pressed()

  display.flip()

quit()
```

- Python and Pygame Site: http://programarcadegames.com/index.php

- Java File Picker

```
import javax.swing.*;
import java.util.*;
import java.awt.*;
import java.awt.event.*;


public class FilePick extends JFrame implements ActionListener{
    public FilePick(){
		super ("Pick File");
		setSize(800,600);
		JButton show = new JButton("show");
		show.addActionListener(this);
		add(show);
		setDefaultCloseOperation (JFrame.EXIT_ON_CLOSE);
		setVisible (true);
    }

 	public void actionPerformed(ActionEvent e){
	    JFileChooser chooser = new JFileChooser();

	    int returnVal = chooser.showOpenDialog(this);
	    if(returnVal == JFileChooser.APPROVE_OPTION) {
	       System.out.println("You chose to open this file: " + chooser.getSelectedFile().getName());
	    }
	}

    public static void main(String[] args){
		new FilePick();
    }
}
```
- Baseframe (Swing Graphics)

```
/* ----------------------------------------------------------------------------------
 * BaseFrame.java
 * Mr. McKenzie
 * Nov. 13 2009
 * --------------
 * Revised Dec 14 2022
 * -----------------------------------------------------------------------------------
 * BaseFrame is designed to take a lot of the complexity out of doing graphics in Java.
 * The idea is, that rather inhetiting from JFrame directly we place a lot of common
 * code in BaseFrame then inherit from BaseFrame. BaseFrame includes:
 *
 *  - A Timer, with a 20 ms delay that calls move() and repaint()
 * 	- MouseMotionListener, MouseListener, KeyListener
 *	mx,my,mb,keys- these fields are protected so you have direct access to them from the
 *				   inherited class.
 *  - move() - this is a hook that you can use to update the state of your game
 *  - draw() - repaint() calls paint(), this calls the JPanel paint(), which calls draw()
 *			 - The JPanel is used because it automaticly double-buffered. If we draw
 *			   directly to the Frame it will flicker. We call the draw method so that
 *			   when we extend the BaseFrame we can override this method to handle
 *  	   	   our drawing.
 -------------------------------------------------------------------------------------*/


import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.awt.image.*;

class BaseFrame extends JFrame implements MouseMotionListener, MouseListener, KeyListener, ActionListener{
	protected int mx,my,mb;
	protected boolean []keys;

	protected Image back,dbImage;
	protected Graphics dbg;
	protected String col="";
	protected GamePane pane;
	protected Timer timer;

	final protected int LEFT = 37;
	final protected int UP = 38;
	final protected int RIGHT = 39;
	final protected int DOWN = 40;
	final protected int SPACE = 32;
	final protected int ESC = 27;

    public BaseFrame(String t, int w, int h) {
		super(t);
		pane = new GamePane(this);
		pane.setPreferredSize(new Dimension(w, h));

		addKeyListener(this);
		addMouseListener (this);
		addMouseMotionListener(this);

		keys = new boolean[2000];
		add(pane);
		pack();
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setVisible(true);
		timer = new Timer(20, this);
		timer.start();
    }

	private void updateMouse(MouseEvent e){
		mx = e.getX();
		my = e.getY();
	}

    public void mouseEntered(MouseEvent e) {}
    public void mouseExited(MouseEvent e) {}

    public void mouseReleased(MouseEvent e) {
     	updateMouse(e);
     	mb = 0;
    }
    public void mouseClicked(MouseEvent e){
    	updateMouse(e);
    	mb = 0;
    }
    public void mouseDragged(MouseEvent e){
    	updateMouse(e);
	}
    public void mouseMoved(MouseEvent e){
    	updateMouse(e);
	}
    public void mousePressed(MouseEvent e){
    	updateMouse(e);
    	mb = e.getButton();
	}

    public void keyTyped(KeyEvent e) {}

    public void keyPressed(KeyEvent e) {
        keys[e.getKeyCode()] = true;
    }

    public void keyReleased(KeyEvent e) {
        keys[e.getKeyCode()] = false;
    }

	// should be overloaded
	public void move(){

	}

	public void draw(Graphics g){

	}


	@Override
	public void actionPerformed(ActionEvent e){
		move(); 	// never draw in move
		repaint(); 	// only draw
	}

	class GamePane extends JPanel{
		BaseFrame main;

		public GamePane(BaseFrame m){
			main = m;
		}
		public void paint(Graphics g){
			main.draw(g);
		}
	}

}
```

