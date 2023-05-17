static class Ant {
        private int position;
        private int energy;

        public Ant() {
            Random random = new Random();
            position = random.nextInt(100);
            energy = random.nextInt(10) + 1;
        }
