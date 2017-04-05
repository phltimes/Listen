#Wartezeit: Anzahl der Elemente
#New: neues Element am Ende
#Boarding: geht weg

class Warteschlange(object):

    def __init__(self, pListe = []):
        self.liste = pListe

    def enter(self, element):
        self.liste = [element] + self.liste

    def boarding(self):
        if self.liste == []:
            return 'Der Wartebereich ist leer.'
        else:
            self.liste = self.liste[:-1]

    def wartezeit(self):
        if self.liste == []:
            return 'Der Wartebereich ist leer.'
        else:
            print('Anzahl der Menschen im Wartebereich:', len(self.liste), 'Bestehend aus:')
            return self.liste

    def quickpass(self, element):
        self.liste = self.liste + [element]
