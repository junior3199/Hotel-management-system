# Hotel-management-system
#include <stdio.h>
#include<string.h>
struct customer{
            char c_ID[100];
            char c_name[100];
            char c_nationality[100];
            char c_num[100];
            char c_sex[50];
            char c_status[100];
};
struct getCustomer{
            struct customer c[100];
};
int i = 0;

struct getCustomer getCustomerData() {
        struct getCustomer get;
        FILE *file = fopen("./data/customers.txt", "r");
            char c_ID[100];
            char c_name[100];
            char c_nationality[100];
            char c_num[100];
            char c_sex[50];
            char c_status[100];
            i = 0;

    fscanf(file, "%s\t\t\t\t%s\t\t\t\t%s\t\t\t\t%s\t\t\t\t%s",  c_ID, c_name, c_nationality, c_num, c_sex, c_status) ;

    while(fscanf(file, "%s\t\t\t\t%s\t\t\t\t%s\t\t\t\t%s\t\t\t\t%s",  get.c[i].c_ID, get.c[i].c_name, get.c[i].c_nationality, get.c[i].c_num, get.c[i].c_sex, get.c[i].c_status != EOF)){
        i++;
    }
    fclose(file);
    return get;
};
void DisplayAllCustomer(){
        struct customer c[100];
        int i=0;
        FILE *file;
        file= fopen("./data/customers.txt", "r");
        while(fscanf(file, "\n%s\t\t%s\t\t%s\t\t%s\t\t%s\t\t%s\n", c[i].c_ID, c[i].c_name, c[i].c_nationality, c[i].c_num, c[i].c_sex, c[i].c_status) != EOF){
            i++;
        }

        for(int j=0; j<i; j++){
            printf("\n%s\t\t%s\t\t%s\t\t%s\t\t%s\t\t%s\n", c[j].c_ID,c[j].c_name,c[j].c_nationality,c[j].c_num,c[j].c_sex,c[j].c_status);
        }
}
void AddCustomer(){
        struct customer c;
        FILE *file;
        file= fopen("./data/customers.txt", "a+");
        printf("Enter ur ID: ");
        scanf("%s", &c.c_ID);
        printf("Enter a name: ");
        scanf("%s", &c.c_name);
        printf("Enter ur nationality: ");
        scanf("%s", &c.c_nationality);
        printf("Enter ur phone number: ");
        scanf("%s", &c.c_num);
        printf("Enter ur sex: ");
        scanf("%s", &c.c_sex);
        fprintf(file, "%s\t\t%s\t\t%s\t\t%s\t\t%s\n", c.c_ID, c.c_name, c.c_nationality, c.c_num, c.c_sex);
}
//void UpdateCustomerInfo(){
        //struct customer c[100];
        //struct getCustomer get;
        //char update_customer[10];
        //FILE *file;
        //file= fopen("./data/customers.txt", "w");
        //printf("Enter customer ID: ");
        //scanf("%s", &update_customer);
        //for(int j = 0; j<i; j++) {
           // if(strcmp(get.c[j].c_ID, update_customer) == 0 && strcmp(get.c[j].c_status, "active") == 0) {
             //   printf("Customer ID: \t\t%s\n", get.c[j].c_ID);
             //   printf("Customer Name : \t\t%s\n",  get.c[j].c_name);
             //   printf("Customer Nationality: \t\t%s\n",  get.c[j].c_nationality);
             //   printf("Customer Num: \t%s \n",  get.c[j].c_num);
            //    printf("Customer Sex: \t%s \n",  get.c[j].c_sex);
             //   printf("Customer Status: \t\t%s\n", get.c[j].c_status);

               // char customer_name[100];
             //   char customer_nationality[100];
             //   char customer_num[100];
             //   char customer_sex[100];

             //   printf("Enter customer name: ");
                //scanf("%s", &customer_name);
              //  printf("Enter customer nationality: ");
             //   scanf("%d", &customer_nationality);
             //   printf("Enter customer phone number: ");
               // scanf("%d", &customer_num);
              //  printf("Enter customer sex: ");
              //  scanf("%d", &customer_sex);

               // for(int j = 0; j<i; j++) {
             //       if(strcmp(get.c[j].c_ID, update_customer) == 0 && strcmp(get.c[j].c_status, "active") == 0) {
             //           get.c[j].c_name = customer_name;
             //           get.c[j].c_nationality = customer_nationality;
               //         get.c[j].c_num = customer_num;
               //         get.c[j].c_sex = customer_sex;
               //     }
              //  }

          //  FILE *write_file = fopen("./data/customers.txt", "w");
          //  fprintf(write_file, "\ncustomer_id\t\t\tcustomer_name\t\tcustomer_nationality\t\tcustomer_num\t\tcustomer_sex\t\troom_status");
          //  for(int k = 0; k< i; k++) {
          //      fprintf(write_file, "\n%s\t\t\t%s\t\t\t\t%s\t\t\t\t%s\t\t\t\t%s\t\t\t%s", get.c[k].c_ID, get.c[k].c_name, get.c[k].c_nationality, get.c[k].c_num, get.c[k].c_sex,get.c[k].c_status);
          //  }
          //  fclose(write_file);
          //  return;
    //    }
    //}

//    printf("Customer ID is not existed.\n");
   // }
void DeleteCustomer(){
        struct getCustomer get = getCustomerData();
        char delete_customer_id[100];

        printf("Enter customer ID: ");
        scanf("%s", &delete_customer_id);

        for(int j = 0; j< i; j++) {
            if(strcmp(get.c[j].c_ID, delete_customer_id) == 0) {
                strcpy(get.c[j].c_status, "deleted");
            }
        }

        FILE *write_file = fopen("./data/customers.txt", "w");
        fprintf(write_file, "\ncustomer_id\t\t\tcustomer_name\t\tcustomer_nationality\t\tcustomer_num\t\tcustomer_sex\t\troom_status");
        for(int k = 0; k< i; k++) {
                fprintf(write_file, "\n%s\t\t\t%s\t\t\t\t%s\t\t\t\t%s\t\t\t\t%s\t\t\t%s", get.c[k].c_ID, get.c[k].c_name, get.c[k].c_nationality, get.c[k].c_num, get.c[k].c_sex,get.c[k].c_status);
            }
        fclose(write_file);
}
int main(){

        DisplayAllCustomer();
        AddCustomer();
        //UpdateCustomerInfo();
        DeleteCustomer();
}

