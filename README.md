
#include <stdio.h>
#include<string.h>

int main()
{
    char username[20], password[20];
    int choice, quantity;
    float price, total, gst, grandTotal;

   
    printf("RESTAURANT BILLING SYSTEM \n");
    

    
    printf("\n LOGIN \n");

    printf("Enter Username: ");
    scanf("%s", username);

    printf("Enter Password: ");
    scanf("%s", password);

    if (strcmp(username, "admin") == 0 &&
        strcmp(password, "1234") == 0)
    {
        printf("\n Login Successful \n");

        printf("\nFOOD MENU \n");
        printf("1. Idli - Rs.40 \n");
        printf("2. Dosa - Rs.60 \n");
        printf("3. Fried Rice - Rs.100\n");
        printf("4. Biriyani - Rs.150\n");
        printf("5. Coffee - Rs.30 \n");

        printf("\n Enter your choice (1-5): ");
        scanf("%d", &choice);

        printf("Enter quantity: ");
        scanf("%d", &quantity);

        if (choice == 1)
        {
            price = 40;
            printf("\nItem: Idli \n");
        }
        else if (choice == 2)
        {
            price = 60;
            printf("\nItem: Dosa \n");
        }
        else if (choice == 3)
        {
            price = 100;
            printf("\nItem: Fried Rice \n");
        }
        else if (choice == 4)
        {
            price = 150;
            printf("\n Item: Biriyani \n");
        }
        else if (choice == 5)
        {
            price = 30;
            printf("\n Item: Coffee \n");
        }
        else
        {
            printf("\n Invalid choice \n");
            return 0;
        }

        total = price * quantity;
        gst = total * 0.05;
        grandTotal = total + gst;

        printf("Price: Rs. %.2f \n", price);
        printf("Quantity: %d\n", quantity);
        printf("Total : Rs. %.2f \n", total);
        printf("GST (5%%) : Rs. %.2f \n", gst);
        printf("Grand Total : Rs. %.2f\n", grandTotal);

        
        printf("THANK YOU VISIT AGAIN \n");
        
    }
    else
    {
        printf("\n Wrong Username or Password \n");
        printf("Login Failed \n");
    }

    return 0;
}
