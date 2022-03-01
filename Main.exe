#!/usr/bin/env python3

wordsHandle = open("words5.txt")
words = []
for word in wordsHandle:
    words.append(wordsHandle.readline().rstrip())

#Find most common letter
alphabet = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']
print(f"Your Starter is Beans.")
solutions = words
solutionsBuffer = []
def Find(letterarray,indexarray):
    global solutions,solutionsBuffer
    try:
        for word in solutions:
            if word !='':
                for entry in range(len(letterarray)):
                    if letterarray[entry] == word[indexarray[entry]]:
                        solutionsBuffer.append(word)
        solutions = [None]*len(solutionsBuffer)
        for i in range(len(solutionsBuffer)):
            solutions[i]=solutionsBuffer[i]
        solutionsBuffer = []
        return solutions
    except:
        print("error in formatting of entry. Try to put a space between the letter and number")
def FindWithout(letternot):
    global solutions,solutionsBuffer
    index = len(solutions)-1
    while index >= 0:
        if solutions[index] !='':
            for letter in solutions[index]:
                if letter==letternot:
                    solutions.pop(index)
        index -= 1
    return solutions

def findyellow(letternot,indexnot):
    global solutions, solutionsBuffer
    index = len(solutions)-1
    indexnot = indexnot[0] # And this line too bcos of 0s
    letternot = letternot[0]
    while index >= 0:
        letterfound = False
        word = solutions[index]

        if word!='':
            letterfound = False
            for letter in word:
                if letter == letternot: # If entering multiple indexes this line needs a fix
                    letterfound = True
                    if word[indexnot] == letternot: 
                        solutions.pop(index)
            if letterfound == False:
                solutions.pop(index)
        index -=1
    return solutions
                


#What would you like to input - one at a time letter and index
#Always use solutions for the search
def Main():
    run = True
    while run:
        RequestRequest = input("What would you like to input (Green: G, Grey: Gr or Yellow: Y.  ").rstrip().lower()
        if RequestRequest == "g":
            GRequest = input("Enter one green letter and it's index: ").lower().rstrip().split(" ")
            GRequestDigits = []
            GRequestLetters = []
            for input1 in GRequest:
                if input1.isdigit():
                    GRequestDigits.append(int(input1))
                else:
                    GRequestLetters.append(input1.lower())
            FunctionReturn = []
            FunctionReturn.append(Find(GRequestLetters,GRequestDigits))
            print(f"Options: {FunctionReturn}")
        elif RequestRequest =="gr":
            GrRequest = input("Enter one grey letter: ").lower().rstrip()
            FunctionReturn = []
            FunctionReturn.append(FindWithout(GrRequest))
            print(f"Options: {FunctionReturn}")
        elif RequestRequest =="y":
            YRequest = input("Enter one yellow letter and index: ").lower().rstrip().split(" ")
            YRequestDigits = []
            YRequestLetters = []
            for input1 in YRequest:
                if input1.isdigit():
                    YRequestDigits.append(int(input1))
                else:
                    YRequestLetters.append(input1.lower())
            FunctionReturn = []
            FunctionReturn.append(findyellow(YRequestLetters,YRequestDigits))
            print(f"Options: {FunctionReturn}")
        else:
            print("incorrect entry.")
Main()