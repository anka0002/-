import java.util.Stack;

public class ParenthesisChecker {

    public static boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();

        for (char c : s.toCharArray()) {
            if (c == '(') {
                stack.push(c); // Добавляем открывающую скобку в стек
            } else if (c == ')') {
                if (stack.isEmpty()) {
                    return false; // Если стек пуст, значит нет соответствующей открывающей скобки
                }
                stack.pop(); // Удаляем последнюю открывающую скобку из стека
            }
        }

        return stack.isEmpty(); // Если стек пуст, все скобки корректны
    }

    public static void main(String[] args) {
        // Примеры использования
        System.out.println(isValid("()")); // true
        System.out.println(isValid("(()()((())))")); // true
        System.out.println(isValid("(((())()")); // false
    }
}
