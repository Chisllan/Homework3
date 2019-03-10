# Homework3.1
import csv

#pbank = "../Tareas/Homwwork3/budget2.csv"
pbank = "./budget2.csv"

numeroMeses = 0
total_AVLOS = 0
changes_AVLOS = 0

with open(pbank) as csvfile:
    # Motor de lectura
    csvreader = csv.reader(csvfile)
    # csvreader es cada row de mi archivo
    header = next(csvreader)    
    primerLinea = next(csvreader)
    old_AVLOS = int(primerLinea[2])
    total_AVLOS = int(primerLinea[2])
    great_inc=primerLinea
    great_dec=primerLinea

    for x in csvreader:
        numeroMeses += 1
        total_AVLOS += int(x[2])
        changes_AVLOS += int(x[2]) - old_AVLOS
        old_AVLOS = int(x[2])
        if great_inc[2] < x[2]:
            great_inc = x
        if great_dec[2] > x[2]:
            great_dec = x
great_inc2=great_inc[1]
great_inc3=great_inc[2]
great_dec2=great_dec[1]
great_dec3=great_dec[2]
print("--------------------------------------------")    
print("Number of Months :" + str(numeroMeses))
print("\n")
print("Total de values: $" + str(total_AVLOS))
print("\n")
print("Average: $" + str(changes_AVLOS / numeroMeses))
print("\n")
print("Greatest Increase in Profits: " + str(great_inc2) + "( $" + str(great_inc3) + ")")
print("\n") 
print("Greatest Decrease in Profits: " + str(great_dec2) + "( $" + str(great_dec3) + ")")



#Homework 3.2

import csv

#pbank = "../Tareas/Homework3/budget2.csv"
pvotes = "./election_data.csv"

numeroVotos = 0
changes_AVLOS = 0

with open(pvotes) as csvfile:
    # Motor de lectura
    csvreader = csv.reader(csvfile)
    # csvreader es cada row de mi archivo
    header = next(csvreader)    
    primerLinea = next(csvreader)
    t_votos=0
    w=0
    m=0
    y=0
    z=0
    #Khan, Correy, Li, O'Tooley

    for x in csvreader:
        numeroVotos = numeroVotos + 1
        if x[2] == "Khan":
            w = w + 1
        if x[2] == "Correy":
            m = m + 1
        if x[2] == "Li":
            y = y + 1
        if x[2] == "O'Tooley":
            z = z + 1
    
        
    Khan_por= (w/numeroVotos)*100
    Correy_por = (m/numeroVotos)*100
    Li_por = (y/numeroVotos)*100
    Otolley_por = (z/numeroVotos)*100

print("--------------------------------------------")    
print("Results")
print("\n")
print("The total number of votes: " + str(numeroVotos))
print("\n")
print("Khan : " + str(Khan_por)+" % " + "(" + str(w)+")")
print("Correy : " + str(Correy_por)+" % " + "(" + str(m)+")")
print("Li : " + str(Li_por)+" % " + "(" + str(y)+")")
print("O'Tooley : " + str(Otolley_por)+" % " + "(" + str(z)+")")
print("\n")
print("The winner is Khan")
