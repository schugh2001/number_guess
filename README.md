# number_guess
class game:
    def yes(self):
        import random
        lowerbound=int(input('enter a lowerbound \n'))
        upperbound=int(input('enter a upperbound \n'))
        random_no=random.randint(lowerbound,upperbound)
        print('''Hey! the game starts now,
         You have only 5 chance
         BEST OF LUCK''')
        count=0
        for i in range(0,5):
            count+=1
            print('enter your guess_no {} \n'.format(count))
            s=input().lower()
            if s=='hint':
                print('you will lose one chance')
                guess_no=0
            else:
                guess_no=int(s)
                if guess_no not in range(lowerbound,upperbound):
                    print('You break the rule DISQUALIFIED')
                    self.e()
            diff=guess_no-random_no
            if guess_no==random_no:
                print('BRAVO! your guess is correct')
                self.e()
            if count==5:
                print('Better luck next time')
                print('The correct no.is {}'.format(random_no))
                self.e()
            if s=='hint':
                print("Number is between {},{}".format(random_no-5,random_no+5))
            if guess_no!=random_no and abs(diff)<=10 and s.lower()!='hint':
                print('You are almost there')
            if guess_no!=random_no and 10<abs(diff)<=30 and s.lower()!='hint':
                print('You are not much far')
            if guess_no!=random_no and abs(diff)>30 and s.lower()!='hint':
                print()
           

    def e(self):
        print('do you really want to exit')
        print('enter y or n')
        a=input().lower()
        if a=='y':
            exit()
        if a=='n':
            self.yes()
        
sid=game()
sid.yes()


