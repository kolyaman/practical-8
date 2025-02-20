Практична робота №8 Мануйленко Микола

    #include <stdio.h>
    #include <string.h>

    unsigned long long compute_factorial(int num) {
    unsigned long long product = 1;
    for (int i = 1; i <= num; i++) {
        product *= i;
    }
    return product;
    }

    int main() {
    char input_word[15];
    scanf("%s", input_word);

    int word_length = strlen(input_word);
    int char_count[26] = {0};

    for (int j = 0; j < word_length; j++) {
        char_count[input_word[j] - 'A']++;
    }

    unsigned long long total_permutations = compute_factorial(word_length);
    for (int j = 0; j < 26; j++) {
        if (char_count[j] > 0) {
            total_permutations /= compute_factorial(char_count[j]);
        }
    }

    printf("%llu\n", total_permutations);
    return 0;
    }
