# AntColonySimulation
AntColonySimulation
import java.util.Random;

public class AntColonySimulation {
    public static void main(String[] args) {
        int colonySize = 100;
        Ant[] colony = new Ant[colonySize];

        // Инициализация колонии муравьев
        for (int i = 0; i < colonySize; i++) {
            colony[i] = new Ant();
        }

        // Симуляция жизни колонии муравьев
        for (int day = 1; day <= 365; day++) {
            System.out.println("День " + day + ":");
            for (Ant ant : colony) {
                ant.move();
                ant.eat();
                ant.reproduce();
            }
            System.out.println("-------------------------------");
        }
    }

    static class Ant {
        private int position;
        private int energy;

        public Ant() {
            Random random = new Random();
            position = random.nextInt(100);
            energy = random.nextInt(10) + 1;
        }

        public void move() {
            Random random = new Random();
            int newPosition = position + random.nextInt(11) - 5;
            if (newPosition >= 0 && newPosition < 100) {
                position = newPosition;
            }
        }

        public void eat() {
            energy += 3;
        }

        public void reproduce() {
            if (energy >= 10) {
                energy -= 10;
                Ant babyAnt = new Ant();
                System.out.println("Муравей размножился!");
            }
        }
    }
}
