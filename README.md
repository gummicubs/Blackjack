#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
    srand(time(0));
    cout << "Get ready to play Blackjack! \n" << endl;
    cout << "WARNING: This dealer does not know how to split.\n";

int j = 0;//1 if player gets an Ace
int k = 0;//1 if dealer gets an Ace
int x = 0;//number of cards for player
int y = 0;//number of cards for the dealer
int a[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13};
    
int card1 = a[rand()%12];
x++;

switch (card1){
    case 1:
        cout << "Your first card is an Ace.\n\n";
        j = 1;
        break;
    case 11:
        cout << "Your first card is a Jack.\n\n";
        break;
    case 12:
        cout << "Your first card is a Queen.\n\n";
        break;
    case 13:
        cout << "Your first card is a King.\n\n";
        break;
    default:
        cout << "Your first card is " << card1 << ".\n\n";
}

int deal1 = a[rand()%12];
y++;
cout << "The dealer got a card faced down.\n\n";


int card2 = a[rand()%12];
x++;
switch (card2){
    case 1:
        cout << "Your second card is an Ace.\n\n";
        j = 1;
        break;
    case 11:
        cout << "Your second card is a Jack.\n\n";
        break;
    case 12:
        cout << "Your second card is a Queen.\n\n";
        break;
    case 13:
        cout << "Your second card is a King.\n\n";
        break;
    default:
        cout << "Your second card is " << card2 << ".\n\n";
}

if (card1 > 10) {
    card1 = 10;
}

if (card2 > 10) {
    card2 = 10;
}

int deal2 = a[rand()%12];
y++;
switch (deal2){
    case 1:
        cout << "The dealer's face up card is an Ace.\n\n";
        k = 1;
        break;
    case 11:
        cout << "The dealer's face up card is a Jack.\n\n";
        break;
    case 12:
        cout << "The dealer's face up card is a Queen.\n\n";
        break;
    case 13:
        cout << "The dealer's face up card is a King.\n\n";
        break;
    default:
        cout << "The dealer's face up card is " << deal2 << ".\n\n";
}

if (deal2 > 10) {
    deal2 = 10;
}

if (j == 1 && (card1 == 10 || card2 == 10)) {
    cout << "You got a Blackjack! Let's see what the dealer gets.\n\n";
     switch (deal1){
    case 1:
        cout << "The dealer's face down card is an Ace. \n";
        k = 1;
        break;
    case 11:
        cout << "The dealer's face down card is a Jack.\n";
        break;
    case 12:
        cout << "The dealer's face down card is a Queen.\n";
        break;
    case 13:
        cout << "The dealer's face down card is a King.\n";
        break;
    default:
        cout << "The dealer's face down card is " << deal1 << ".\n";
    }
    if (k == 1 && (deal2 > 9 || deal2 >9)) {
            cout << "The dealer also got a BlackJack! It's a tie!\n";
        }
    else {
        cout << "The dealer does not have Blackjack. Congratulations! You won!\n\n";
    }}
    
else if (k == 1 && (deal1 > 9 || deal2 > 9)) {
        switch (deal1){
         case 1:
        cout << "The dealer's face down card is an Ace. \n";
        k = 1;
        break;
         case 11:
        cout << "The dealer's face down card is a Jack.\n";
        break;
         case 12:
        cout << "The dealer's face down card is a Queen.\n";
        break;
         case 13:
        cout << "The dealer's face down card is a King.\n";
        break;
         default:
        cout << "The dealer's face down card is " << deal1 << ".\n";
        }
        cout << "The dealer has Blackjack! Dealer wins!";
        }
    
else {
    int sum = card1 + card2;
    int altsum = sum + 10;
    if (j == 1) {
        cout << "Your current total is " << sum << " or " << altsum << ". \nWould you like to hit or stand?\n\n";
    }
    else {
        cout << "Your current total is " << sum << ". \nWould you like to hit or stand?\n\n";
    }
    if (card1==card2) {
        cout << "Or would you like to split?\n\n";
        }

    string b;  
    cin >> b;
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    while (b == "hit" && x < 6) {
        int card3 = a[rand()%12];
        x++;
        cout << "You have chosen to get another card.\n";
        switch (card3){
    case 1:
        cout << "You were dealt an Ace.\n";
        j = 1;
        break;
    case 11:
        cout << "You were dealt a Jack.\n";
        break;
    case 12:
        cout << "You were dealt a Queen.\n";
        break;
    case 13:
        cout << "You were dealt a King.\n";
        break;
    default:
        cout << "You were dealt a " << card3 << ".\n";
        }
        if (card3 > 10){
            card3 = 10;
        }
        sum = sum + card3;
        cout << "Your new total is " << sum;
        if (j == 1) {
            altsum = sum + 10;
            cout << " or " << altsum;
            }
            cout << ".\n\n";
        if (x == 5 && sum < 22) {
            cout << "You were dealt five cards. You automatically win!";
            return 0;
            }
        if (sum < 21) {
            cout << "Would you like to hit or stand?\n\n";
            cin >> b;
            }
        if (sum > 21) {
            cout << "You got BUSTED!";
            return 0;
            }
        if (sum == 21) {
            cout << "You got 21! Let's see if you beat the dealer.\n\n";
            b = "stand";
        }
    }











 if (b == "stand") {
      if (j == 1) {
        if (altsum < 22) {
            sum = altsum;
            cout << sum;
        }}
    switch (deal1){
    case 1:
        cout << "The dealer's face down card is an Ace.\n";
        k = 1;
        break;
    case 11:
        cout << "The dealer's face down card is a Jack.\n";
        break;
    case 12:
        cout << "The dealer's face down card is a Queen.\n";
        break;
    case 13:
        cout << "The dealer's face down card is a King.\n";
        break;
    default:
        cout << "The dealer's face down card is " << deal1 << ".\n";
    }
    if (deal1 > 10) {
    deal1 = 10;
    }
    
    int dsum = deal1 + deal2;
    int altdsum = dsum + 10;
    cout << "The dealer's total is " << dsum;
        if (k == 1) {
            cout << " or " << altdsum;
        }
        cout << ".\n";
        
        while ((!(dsum > sum) && dsum < 17 && !(k == 1) || (k == 1 && altdsum < 17 && !(altdsum > sum))) && y < 6) {
            cout << "The dealer deals himself another card.\n\n";
            int deal3 = a[rand()%12];
            y++;
        switch (deal3) {
        case 1:
        cout << "The dealer deals himself an Ace.\n\n";
        k = 1;
        break;
        case 11:
        cout << "The dealer deals himself a Jack.\n\n";
        break;
        case 12:
        cout << "The dealer deals himself a Queen.\n\n";
        break;
        case 13:
        cout << "The dealer deals himself a King.\n\n";
        break;
        default:
        cout << "The dealer deals himself a " << deal3 << ".\n\n";
        }
        if (deal3 > 10) {
            deal3 = 10;
        }
        
        dsum = dsum + deal3;
        cout << "The dealer 's total is " << dsum; 
        if (k == 1) {
            altdsum = dsum + 10;
            if (altdsum < 22) {
            cout << " or " << altdsum;
            }
        }
         cout << ".\n\n";
        }
        if (y < 5) {
            if ((dsum > sum && dsum < 22 && !(k == 1)) || (k == 1 && altdsum > sum && altdsum < 22)) {
            cout << "The dealer's final total is greater than yours. \nThe dealer wins!";
            }
            if (dsum > sum && dsum > 21) {
            cout << "The dealer BUTSTED!! \n Congratulations! You win!";
            }
            if ((dsum < sum && !(k == 1)) || (k == 1 && altdsum < sum)) {
            cout << "Your total is greater than the dealer's total. \nCongratulations! You win!";
            }
            if ((dsum == sum && !(k == 1)) || (k == 1 && altdsum == sum)) {
            cout << "The dealer has the same final total as you. \nIt's a tie!";
            }
        }
        if (y == 5 && dsum < 22) {
            cout << "Dealer has five cards. Dealer automatically wins!";
        }
     
 }
        
        
        


}
    return 0;
}
