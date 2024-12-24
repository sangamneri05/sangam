#include <stdio.h>
#include <string.h>

void reverseString(char str[]) {
    int start = 0;
    int end = strlen(str) - 1;
    char temp;

    while (start < end) {
        // Swap the characters
        temp = str[start];
        str[start] = str[end];
        str[end] = temp;

        // Move the pointers
        start++;
        end--;
    }
}

int main() {
    char str[100];

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    // Remove trailing newline character, if present
    size_t len = strlen(str);
    if (len > 0 && str[len - 1] == '\n') {
        str[len - 1] = '\0';
    }

    reverseString(str);

    printf("Reversed string: %s\n", str);

    return 0;
}
