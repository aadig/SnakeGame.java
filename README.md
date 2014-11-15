SnakeGame.java
==============
package ArrayFun;

import zen.core.Zen;

public class SnakeGame {

	public static void main(String[] args) {
		Zen.create(500, 500);

		Snake head = new Snake();
		Food snakeFood = new Food();


		while (true) {
			Zen.setBackground("orange");

			snakeFood.draw();
			if (snakeFood.x == head.x && snakeFood.y == head.y) {
				head.grow();
				snakeFood = new Food();
			}

			head.draw();
			head.move();
			head.checkKeys();

			if(head.dead()) {
				head.die();
			}

			if (Zen.isKeyPressed("space")) {
				head.grow(); 
			}

			Zen.buffer(33);
		}

	}

}
