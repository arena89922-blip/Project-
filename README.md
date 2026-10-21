
#include <stdio.h>
#include <string.h>

int main()
{
    char username[20], password[20];
    int choice, quantity;
    float total, gst, grandTotal;

    // Arrays to store the food menu data
    int itemIds[5] = {1, 2, 3, 4, 5};
    char *itemNames[5] = {"Idli", "Dosa", "Fried Rice", "Biriyani", "Coffee"};
    float itemPrices[5] = {40.00, 60.00, 100.00, 150.00, 30.00};

    printf("=========================================\n");
    printf("        ARAMANE DONNE BIRYANI            \n");
    printf("=========================================\n");
    
    printf("\n--- LOGIN ---\n");
    printf("Enter Username: ");
    scanf("%19s", username);

    printf("Enter Password: ");
    scanf("%19s", password);

    if (strcmp(username, "admin") == 0 && strcmp(password, "1234") == 0)
    {
        printf("\n>>> Login Successful! <<<\n");

        printf("\n============== FOOD MENU ==============:\n");
        for (int i = 0; i < 5; i++)
        {
            printf("%d. %-12s - Rs. %.2f\n", itemIds[i], itemNames[i], itemPrices[i]);
        }
        printf("=======================================\n");

        printf("\nEnter your choice (1-5): ");
        scanf("%d", &choice);

        // Validate choice using array bounds
        if (choice < 1 || choice > 5)
        {
            printf("\n>>> Invalid choice! Program terminated. <<<\n");
            return 0;
        }

        printf("Enter quantity: ");
        scanf("%d", &quantity);

        if (quantity <= 0)
        {
            printf("\n>>> Invalid quantity! Program terminated. <<<\n");
            return 0;
        }

        // Get index based on choice (Choice 1 is at index 0)
        int index = choice - 1;
        float price = itemPrices[index];

        // Calculations
        total = price * quantity;
        gst = total * 0.05;
        grandTotal = total + gst;

        // Separate Structured Bill Format
        printf("\n\n=========================================\n");
        printf("        ARAMANE DONNE BIRYANI            \n");
        printf("            OFFICIAL RECEIPT             \n");
        printf("=========================================\n");
        printf("Item Ordered  : %s\n", itemNames[index]);
        printf("Unit Price    : Rs. %.2f\n", price);
        printf("Quantity      : %d\n", quantity);
        printf("-----------------------------------------\n");
        printf("Subtotal      : Rs. %.2f\n", total);
        printf("GST (5%%)      : Rs. %.2f\n", gst);
        printf("-----------------------------------------\n");
        printf("GRAND TOTAL   : Rs. %.2f\n", grandTotal);
        printf("=========================================\n");
        printf("       THANK YOU! PLEASE VISIT AGAIN     \n");
        printf("=========================================\n");
    }
    else
    {
        printf("\n>>> Wrong Username or Password! <<<\n");
        printf(">>> Login Failed. <<<\n");
    }

    return 0;
}
