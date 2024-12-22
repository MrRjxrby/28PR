# 28PR
# Практика 28
# Задание 1
```
import java.util.HashSet;
import java.util.TreeSet;

public class HashSetToTreeSet {
    public static void main(String[] args) {
        HashSet<String> hashSet = new HashSet<>();
        hashSet.add("plane");
        hashSet.add("computer");
        hashSet.add("bread");

        TreeSet<String> treeSet = new TreeSet<>(hashSet);
    }
}
```
# Задание 2
```
import java.util.HashMap;
import java.util.Map;

public class NameMap {
    public static void main(String[] args) {
        Map<String, String> nameMap = createMap();
        int sameFirstNameCount = gSFNC(nameMap);
        int sameLastNameCount = gSLNC(nameMap);
    }

    private static Map<String, String> createMap() {
        Map<String, String> map = new HashMap<>();
        map.put("Иванов", "Георгрий");
        map.put("Петров", "Петр");
        map.put("Сидоров", "Иван");
        map.put("Кочкин", "Сергей");
        map.put("Смирнов", "Дмитрий");
        map.put("Горбунов", "Владислав");
        map.put("Захаров", "Игорь");
        map.put("Вовк", "Егор");
        map.put("Кончаров", "Иван");
        map.put("Соловьев", "Дмитрий");
        return map;
    }

    private static int gSFNC(Map<String, String> map) {
        Map<String, Integer> firstNameCount = new HashMap<>();
        for (String firstName : map.values()) {
            firstNameCount.put(firstName, firstNameCount.getOrDefault(firstName, 0) + 1);
        }

        int count = 0;
        for (int value : firstNameCount.values()) {
            if (value > 1) {
                count += value;
            }
        }
        return count;
    }

    private static int gSLNC(Map<String, String> map) {
        Map<String, Integer> lastNameCount = new HashMap<>(map.size());
        for (String lastName : map.keySet()) {
            lastNameCount.put(lastName, lastNameCount.getOrDefault(lastName, 0) + 1);
        }

        int count = 0;
        for (int value : lastNameCount.values()) {
            if (value > 1) {
                count += value;
            }
        }
        return count;
    }
}
```
