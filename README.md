# code-comprehension
# made a python code and a c code building a metro fare collection 
# to firstly get the number of passengers
no_of_passengers = int(input("Enter number of passengers: "))
revenue_collected_so_far = 0
# to input the distance travelled by each passenger
for i in range(1, no_of_passengers + 1):
    distance = float(input(f"enter distance travelled by each passenger so far in kilometres {i}: "))
    if distance < 0:
        print("distance cannot be negative, you learned in 6thgrade")
        continue # used "continue" so that it skips this loop and goes to next condition
    if distance < 5:
        revenue_collected_so_far += 10
    elif distance <= 15:
        revenue_collected_so_far += 20
    elif distance > 15:
        revenue_collected_so_far += 30
print(f"the total revenue collected: {revenue_collected_so_far}")

# now the c code
#include <stdio.h>
int main() {
    int n, i;
    float distance;
    float totalRevenue;
    printf("Enter the number of passengers: ");
    scanf("%d", &n);
    for(i = 1; i <= n; i++) {
        printf("Enter distance traveled by passenger %d (in km): ", i);
        scanf("%f", &distance);

        if(distance < 0) {
            printf("Invalid input! Distance cannot be negative.\n");
            continue;
        }
        if(distance < 5 ){
            totalRevenue += 10;}
        else if(distance <= 15){
            totalRevenue += 20;}
        else{
            totalRevenue += 30;}
    }
    printf("Total revenue collected: Rs.%.2f\n", totalRevenue);
    return 0;
}
