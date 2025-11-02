#include <stdio.h>
#include <string.h>

struct Account {
    char name[50];
    int id;
    float balance;
};

int main() {
    struct Account acc = {"Rainers", 1001, 500.0};
    int choice;
    float amount;

    while (1) {
        printf("\n1. Check Balance\n2. Deposit\n3. Withdraw\n4. Exit\nChoose: ");
        scanf("%d", &choice);

        if (choice == 1)
            printf("Balance: €%.2f\n", acc.balance);
        else if (choice == 2) {
            printf("Enter deposit amount: ");
            scanf("%f", &amount);
            acc.balance += amount;
            printf("Deposited successfully.\n");
        } else if (choice == 3) {
            printf("Enter withdrawal amount: ");
            scanf("%f", &amount);
            if (amount > acc.balance) printf("Insufficient balance!\n");
            else {
                acc.balance -= amount;
                printf("Withdrawal successful.\n");
            }
        } else if (choice == 4) break;
        else printf("Invalid choice!\n");
    }
    return 0;
}
