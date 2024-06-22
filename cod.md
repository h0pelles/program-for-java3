import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class TextTransformer {

    public static void main(String[] args) {
        String inputText = "h0pelles";

        String transformedText = transformText(inputText);
        System.out.println(transformedText);
    }

    public static String transformText(String text) {
        Pattern pattern = Pattern.compile("\\b\\w+\\b|\\W+");
        Matcher matcher = pattern.matcher(text);

        StringBuilder result = new StringBuilder();

        while (matcher.find()) {
            String word = matcher.group();
            if (word.matches("\\w+")) {
                String transformedWord = word.substring(1) + word.charAt(0) + "ауч";
                result.append(transformedWord);
            } else {
                result.append(word);
            }
        }

        return result.toString();
    }
}
