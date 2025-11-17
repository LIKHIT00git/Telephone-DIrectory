#include <stdio.h>
struct directory {
    char name[30];
    char phone[15];
    char area[30];
};
int main() {
    struct directory dir[5] = {
        {"Ravindra_Jadeja", "7465873647", "Pune"},
        {"Virat_Kohli", "9404884040", "Pune"},
        {"Praneel_Batchmate", "7447473838", "Pune"},
        {"Narendra_Modi", "7463529876", "Mumbai"},
        {"Rahul_Gandhi", "9783456784", "Nagpur"}
    };
    char num[15];
    int i, j, same, found = 0;
    printf("Enter phone number to search: ");
    scanf("%s", num);
    for (i = 0; i < 5; i++) {
        same = 1;  
        for (j = 0; num[j] != '\0' || dir[i].phone[j] != '\0'; j++) {
            if (num[j] != dir[i].phone[j]) {
                same = 0;
                break;
            }
        }
        if (same == 1) {
            printf("Name: %s\n", dir[i].name);
            printf("Location/Area: %s\n", dir[i].area);
            found = 1;
            break;
        }
    }
        if (found == 0) {
        printf("Number not found in directory.\n");
    }
     return 0;
}
