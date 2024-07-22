
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_CONTACTS 100
#define MAX_NAME_LEN 50
#define MAX_EMAIL_LEN 50
#define MAX_DOB_LEN 10
#define MAX_CATEGORY_LEN 20

typedef struct {
    char name[MAX_NAME_LEN];
    int number;
    char email[MAX_EMAIL_LEN];
    char dob[MAX_DOB_LEN];
    char category[MAX_CATEGORY_LEN];
} Contact;

Contact phonebook[MAX_CONTACTS];
int num_contacts = 0;

void initial_phonebook() {
    int rows, cols = 5;
    printf("Please enter initial number of contacts: ");
    scanf("%d", &rows);

    for (int i = 0; i < rows; i++) {
        printf("\nEnter contact %d details in the following order (ONLY):\n", i + 1);
        printf("NOTE: * indicates mandatory fields\n");
        printf("....................................................................");;

        printf("Enter name*: ");
        scanf("%s", phonebook[num_contacts].name);

        if (strlen(phonebook[num_contacts].name) == 0) {
            printf("Name is a mandatory field. Process exiting due to blank field...\n");
            exit(1);
        }

        printf("Enter number*: ");
        scanf("%d", &phonebook[num_contacts].number);

        printf("Enter e-mail address: ");
        scanf("%s", phonebook[num_contacts].email);

        printf("Enter date of birth(dd/mm/yy): ");
        scanf("%s", phonebook[num_contacts].dob);

        printf("Enter category(Family/Friends/Work/Others): ");
        scanf("%s", phonebook[num_contacts].category);

        num_contacts++;
    }
}

void menu() {
    printf("********************************************************************\n");
    printf("\t\t\tSMARTPHONE DIRECTORY\n");
    printf("********************************************************************\n");
    printf("\tYou can now perform the following operations on this phonebook\n\n");
    printf("1. Add a new contact\n");
    printf("2. Remove an existing contact\n");
    printf("3. Delete all contacts\n");
    printf("4. Search for a contact\n");
    printf("5. Display all contacts\n");
    printf("6. Exit phonebook\n");

    printf("Please enter your choice: ");
}

void add_contact() {
    if (num_contacts >= MAX_CONTACTS) {
        printf("Phonebook is full. Cannot add more contacts.\n");
        return;
    }

    Contact new_contact;

    printf("Enter name: ");
    scanf("%s", new_contact.name);

    printf("Enter number: ");
    scanf("%d", &new_contact.number);

    printf("Enter e-mail address: ");
    scanf("%s", new_contact.email);

    printf("Enter date of birth(dd/mm/yy): ");
    scanf("%s", new_contact.dob);

    printf("Enter category(Family/Friends/Work/Others): ");
    scanf("%s", new_contact.category);

    phonebook[num_contacts++] = new_contact;
}

void remove_existing() {
    char query[MAX_NAME_LEN];
    printf("Please enter the name of the contact you wish to remove: ");
    scanf("%s", query);

    int found = 0;
    for (int i = 0; i < num_contacts; i++) {
        if (strcmp(query, phonebook[i].name) == 0) {
            found = 1;
            for (int j = i; j < num_contacts - 1; j++) {
                phonebook[j] = phonebook[j + 1];
            }
            num_contacts--;
            printf("This query has now been removed\n");
            break;
        }
    }

    if (!found) {
        printf("Sorry, you have entered an invalid query. Please recheck and try again later.\n");
    }
}

void delete_all() {
    num_contacts = 0;
}

void search_existing() {
    int choice;
    printf("Enter search criteria\n\n");
    printf("1. Name\n2. Number\n3. Email-id\n4. DOB\n5. Category(Family/Friends/Work/Others)\n");
    printf("Please enter: ");
    scanf("%d", &choice);

    int found = 0;
    switch (choice) {
        case 1: {
            char query[MAX_NAME_LEN];
            printf("Please enter the name of the contact you wish to search: ");
            scanf("%s", query);
            for (int i = 0; i < num_contacts; i++) {
                if (strcmp(query, phonebook[i].name) == 0) {
                    printf("Name: %s\nNumber: %d\nEmail: %s\nDOB: %s\nCategory: %s\n",
                           phonebook[i].name, phonebook[i].number, phonebook[i].email,
                           phonebook[i].dob, phonebook[i].category);
                    found = 1;
                }
            }
            break;
        }
        case 2: {
            int query;
            printf("Please enter the number of the contact you wish to search: ");
            scanf("%d", &query);
            for (int i = 0; i < num_contacts; i++) {
                if (query == phonebook[i].number) {
                    printf("Name: %s\nNumber: %d\nEmail: %s\nDOB: %s\nCategory: %s\n",
                           phonebook[i].name, phonebook[i].number, phonebook[i].email,
                           phonebook[i].dob, phonebook[i].category);
                    found = 1;
                }
            }
            break;
        }
        case 3: {
            char query[MAX_EMAIL_LEN];
            printf("Please enter the e-mail ID of the contact you wish to search: ");
            scanf("%s", query);
            for (int i = 0; i < num_contacts; i++) {
                if (strcmp(query, phonebook[i].email) == 0) {
                    printf("Name: %s\nNumber: %d\nEmail: %s\nDOB: %s\nCategory: %s\n",
                           phonebook[i].name, phonebook[i].number, phonebook[i].email,
                           phonebook[i].dob, phonebook[i].category);
                    found = 1;
                }
            }
            break;
        }
        case 4: {
            char query[MAX_DOB_LEN];
            printf("Please enter the DOB (in dd/mm/yyyy format ONLY) of the contact you wish to search: ");
            scanf("%s", query);
            for (int i = 0; i < num_contacts; i++) {
                if (strcmp(query, phonebook[i].dob) == 0) {
                    printf("Name: %s\nNumber: %d\nEmail: %s\nDOB: %s\nCategory: %s\n",
                           phonebook[i].name, phonebook[i].number, phonebook[i].email,
                           phonebook[i].dob, phonebook[i].category);
                    found = 1;
                }
            }
            break;
        }
        case 5: {
            char query[MAX_CATEGORY_LEN];
            printf("Please enter the category of the contact you wish to search: ");
            scanf("%s", query);
            for (int i = 0; i < num_contacts; i++) {
                if (strcmp(query, phonebook[i].category) == 0) {
                    printf("Name: %s\nNumber: %d\nEmail: %s\nDOB: %s\nCategory: %s\n",
                           phonebook[i].name, phonebook[i].number, phonebook[i].email,
                           phonebook[i].dob, phonebook[i].category);
                    found = 1;
                }
            }
            break;
        }
        default:
            printf("Invalid search criteria\n");
            return;
    }

    if (!found) {
        printf("The contact does not exist. Please try again\n");
    }
}

void display_all() {
    if (num_contacts == 0) {
        printf("List is empty: []\n");
    } else {
        for (int i = 0; i < num_contacts; i++) {
            printf("Name: %s\nNumber: %d\nEmail: %s\nDOB: %s\nCategory: %s\n\n",
                   phonebook[i].name, phonebook[i].number, phonebook[i].email,
                   phonebook[i].dob, phonebook[i].category);
        }
    }
}

void thanks() {
    printf("********************************************************************\n");
    printf("Thank you for using our Smartphone directory system.\n");
    printf("Please visit again!\n");
    printf("********************************************************************\n");
    printf("Goodbye, have a nice day ahead!\n");
}

int main() {
    printf("....................................................................");;
    printf("Hello dear user, welcome to our smartphone directory system\n");
    printf("You may now proceed to explore this directory\n");
    printf("....................................................................");;

    initial_phonebook();

    int choice;
    do {
        menu();
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                add_contact();
                break;
            case 2:
                remove_existing();
                break;
            case 3:
                delete_all();
                break;
            case 4:
                search_existing();
                break;
            case 5:
                display_all();
                break;
            case 6:
                thanks();
                return 0;
            default:
                printf("Invalid choice. Please try again.\n");
        }
    } while (choice >= 1 && choice <= 5);

    return 0;
}

/*This C code translates the given Python code for a smartphone directory system. It uses a struct to represent a contact and an array to store the contacts. The main functions are:

- `initial_phonebook()`: Prompts the user to enter the initial number of contacts and their details.
- `menu()`: Displays the menu options.
- `add_contact()`: Adds a new contact to the phonebook.
- `remove_existing()`: Removes an existing contact from the phonebook.
- `delete_all()`: Deletes all contacts from the phonebook.
- `search_existing()`: Searches for a contact based on various criteria (name, number, email, DOB, category).
- `display_all()`: Displays all contacts in the phonebook.
- `thanks()`: Prints a thank you message before exiting the program.

The `main()` function initializes the phonebook, displays the menu, and handles user choices until the user chooses to exit.

Note that this code uses fixed-size arrays and string lengths, so there are limitations on the maximum number of contacts and the lengths of names, emails, DOBs, and categories. You may need to modify the code to handle dynamic memory allocation and variable-length strings for a more robust implementation.
*/
