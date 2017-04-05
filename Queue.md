#-------------------------------------------------------------------------------
# Name:        module1
# Purpose:
#
# Author:      stickphi00
#
# Created:     03.04.2017
# Copyright:   (c) stickphi00 2017
# Licence:     <your licence>
#-------------------------------------------------------------------------------

#Wartezeit: Anzahl der Elemente
#New: neues Element am Ende
#Boarding: geht weg

class Warteschlange(object):

    def __init__(self, pListe = []):
        self.liste = pListe
        global liste
        liste = pListe

    def enter(self, element):
        self.liste = [element] + self.liste
        return self.liste

    def boarding(self):
        if self.liste == []:
            return 'Der Wartebereich ist leer.'
        else:
            self.liste = self.liste[:-1]
            return self.liste

    def wartezeit(self):
        if self.liste == []:
            return 'Der Wartebereich ist leer.'
        else:
            print('Anzahl der Menschen im Wartebereich:', len(self.liste), ' Bestehend aus: ')
            return self.liste
    def quickpass(self, element):
        self.liste = self.liste + [element]




#Ein Tag bei Raik

#10 Uhr: Wartebereich öffnen

raik = Warteschlange()

#10 - 17:45: Die Menschen gehen rein und fahren

zeit = 0

while zeit < 2:
    q = 0
    e = 0
    while q < 21:
        print(raik.enter(q))
        q = q + 1
    q = 0
    while e < 20:
        print(raik.boarding())
        e = e + 1
    e = 0
    print(raik.wartezeit())
    zeit = zeit + 1

#17:45 - 18: Queue leer fahren
while not raik.wartezeit() == 'Der Wartebereich ist leer.':
    print(raik.boarding())

#print(raik.wartezeit())

print('Feierabend')
