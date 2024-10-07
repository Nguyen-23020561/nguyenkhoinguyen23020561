abstract class Animal {
    String name;

    Animal(String name) {
        this.name = name;
    }

    abstract boolean canSwim();
    abstract boolean canWalk();

    public String getName() {
        return name;
    }
}

class Pig extends Animal {
    Pig(String name) {
        super(name);
    }

    @Override
    boolean canSwim() {
        return false;
    }

    @Override
    boolean canWalk() {
        return true;
    }
}

class Duck extends Animal {
    Duck(String name) {
        super(name);
    }

    @Override
    boolean canSwim() {
        return true;
    }

    @Override
    boolean canWalk() {
        return true;
    }
}

class Fish extends Animal {
    Fish(String name) {
        super(name);
    }

    @Override
    boolean canSwim() {
        return true;
    }

    @Override
    boolean canWalk() {
        return false;
    }
}

public class Farm {
    public static void main(String[] args) {
        Animal[] farmAnimals = {
            new Pig("Lợn"),
            new Duck("Vịt"),
            new Fish("Cá")
        };

        printMovableAnimals(farmAnimals);
    }

    static void printMovableAnimals(Animal[] animals) {
        System.out.println("Danh sách động vật có thể bơi hoặc đi bộ:");
        for (Animal animal : animals) {
            if (animal.canSwim() || animal.canWalk()) {
                System.out.println("- " + animal.getName());
            }
        }
    }
}
