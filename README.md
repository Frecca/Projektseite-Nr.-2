# Projektseite zu "Pong Together!"

von Frederik Peters und Rebecca Scholz                                                                                                                                            
Stormarnschule Ahrensburg                                                                                                                                                        
Klasse 12b                                                                                                                                                                        
Schuljahr 2020/2021

## Inhalt

[1. Vorwort](#1)                                                                                                                                                                  
[2. Beschreibung](#2)                                                                                                                                                            
[3. Erläuterungen](#3)                                                                                                                                                            
[3.1 Der Court](#3.1)                                                                                                                                                               
[3.2 Die Player](#3.2)                                                                                                                                                              
[3.3 Der Ball](#3.3)                                                                                                                                                                
[3.4 Der Scorekeeper](#3.4)                                                                                                                                                        
[4. Herausforderungen](#4)                                                                                                                                                          
[5. Schlusswort](#5)

## Vorwort<a name="1"></a>

Unser Spiel *Pong Together!* ist das zweite Projekt, welches wir im Informatikunterricht programmiert haben. Bislang hatten wir nur Kenntnisse in der Programmierung mit Snap! und haben uns mit Greenfoot vertraut machen müssen. Hierfür haben wir das Greenfoot Buch genutzt und im Greenfoot Forum recherchiert. 

*Pong Together!* ist ein Spiel, welches von zwei Spielern gleichzeitig und zusammen gespielt wird. Ziel ist es, den Ball so lang wie möglich hin und her zu spielen. Doch Vorsicht: Der Ball wird schneller! Um hier zu gewinnen müssen die Spieler gut zusammen agieren und schnell reagieren. *Pong Together!* ist eine Neuinterpretation des zeitlosen Klassikers *Pong*, bei dem die Spieler jedoch gegeneinander spielen. 

Auf unserer Projektseite werden wir zunächst unser Spiel beschreiben und dann die einzelnen Funktionen und Zusammenhänge genauer erklären sowie erläutern.

## Beschreibung<a name="2"></a>

Wenn man das Spiel *Pong Togehter!* öffnet, so sieht man zunächst die Spielfläche mit den Spielern und dem Ball, welcher in der Mitte platziert ist. Betätigt man dann die Act-Methode, so erscheint oben in der Mitte der *Score* welcher anzeigt, wie viele *Fails* eingetreten sind, das heißt wie oft der Ball verfehlt wurde. Zu Beginn des Spiels steht der Fail-Score bei 0. 

![Das Spiel](https://github.com/Frecca/Projektblog-Nr.-2/blob/main/Startposition.png)

Das Spiel ist für zwei Spieler programmiert, die gleichzeitig und zusammen spielen und versuchen müssen, den Ball so oft wie möglich hin und her zu passen, ohne ihn zu verpassen und somit einen Fail zu kassieren. Die Steuerung der Spieler erfolgt zum einen über die Pfeiltasten und zum anderen über die Tasten *w* und *s*. 

## Erläuterungen<a name="3"></a>

### Der Court<a name="3.1"></a>

Der Court ist unser Spielfeld. In ihm legen wir die Größe des Spielfeldes fest und definieren, wo sich alle Actor, der Ball und der Score befinden. Dies erfolgt mittels Koordinatenangaben und *add Object*. 
Des Weiteren haben wir hier die Grundgeschwindigkeit des Programms festgelegt. 
Zudem wird auch hier die Verbindung vom Ball zum ScoreKeeper hergestellt und es wird definiert, über welche Tasten sich die einzelnen Spieler steuern lassen. 

![Definition der Objekte](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/1.png)

Hier werden die einzelnen Objekte verortet und die Geschwindigkeit eingestellt:

![Festlegung der Startvoraussetzungen](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/2.png)

### Die Player<a name="3.2"></a>

Die Player sind die Spieler unseres Programms. Jeder von ihnen kann aktiv gesteuert werden und bewegt sich vertikal in einer Ebene auf dem Spielfeld. Um diese in der Programmierung differenzieren zu können, heißt der eine Player *PlayerBlue* und der andere *PlayerRed*. Durch ihre Steuerung muss der Ball hin und her gespielt werden. 

#### Zeichnung und Größe

Sobald sich das Programm öffnet, zeichnen sich die Player selbst. Der Befehl hierfür ist der von uns definierte *void* *drawImage*. Zudem haben wir die Größe der einzelnen Player festgelegt. 

Dies erfolgt mittels der folgenden Programmierung: 

![Zeichnung der Player](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/3.png)

#### Steuerung der Player

Die Steuerung der Player erfolgt über die Tasten *up* und *down* sowie *w* und *s*. Da wir nur eine Player Klasse erstellt haben, wird die Bewegung der Spieler und deren Tastenkombination mittels der Strings *upkey* und *downkey* festgelegt. Im Court ist definiert, mit welchen Tasten welcher Player gesteuert wird. 
Über einen *public void act* definiere wird, wie sich die *y-Koordinate* der Spieler ändert, sodass sie sich vertikal bewegen. 

![Strings](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/4.png)

![Steuerung](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/5.png)

### Der Ball<a name="3.3"></a>

Der Ball ist das Objekt, welches die Spieler hin und her passen müssen. Der Ball bewegt sich zu Beginn des Spiels und nach dem Reset zufällig in eine Richtung. Seine Geschwindigkeit erhöht sich mit jeder Spielerberührung. 

#### Zeichnung, Größe und Geschwindigkeit

Mit der Öffnung des Programms zeichnet sich der Ball, so wie die Player, selbst. Auch hier haben wir die Größe definiert und auch die Ballgeschwindigkeit am Anfang festgelegt. Die Zeichnung des Balls erfolgt über den von uns definierten *void* *drawImage* und ist folgendermaßen programmiert:

![Variablen](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/6.png)

![move speed](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/7.png)

![Zeichnung des Balls](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/8.png)

#### Ball berührt Player

Sobald der Ball einen der Player berührt, agieren diese miteinander und der Ball prallt von den Spielern ab. Seine Bewegungsrichtung erfolgt nach dem Prinzip Einfallswinkel = Ausfallswinkel. Die Geschwindigkeit erhöht sich jedes Mal:

![Ball-Player](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/9.png)


#### Ball berührt Wände

Was passiert, wenn der Ball die Wände berührt? Erreicht er die obere oder andere Kante des Courts, so prallt er auch hier nach dem Prinzip Einfallswinkel = Ausfallswinkel ab, die Geschwindigkeit erhöht sich jedoch nicht.

![Abprall von Wand](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/15.png)

Berührt der Ball jedoch eine der Wände hinter den Playern, so sieht die Programmierung anders und wesentlich komplexer aus. Die Berührung ist in unserem Spiel äquivalent zu einem *Fail*, da der Ball diese möglichst nicht berühren soll. Hier ist auch der ScoreKeeper, nachfolgend erläutert, relevant. Wird nun also eine der Wände berührt, so wird ein *Boolean* Befehl, also eine wahr oder falsch Frage, mit wahr beantwortet. Der Definitionsbereich ist mit der nachfolgenden Programmierung festgelegt und stellt den Bereich dar, in dem sich der Ball hinter den Playern und vor der Außenwand befindet:

![Boolean](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/10.png)

Wird der Boolean mit wahr beantwortet, so wird der Ball auf die Startposition zurückgesetzt, das Spiel für einen kurzen Moment pausiert und eine Nachricht an den ScoreKeeper gesendet. 

![Boolean wahr](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/11.png)

#### Verlinkung zum Scorekeeper

Der Ball benötigt eine Verbindung zum ScoreKeeper, um diesen Nachrichten schicken zu können. Mit Hilfe des [Courts](#3.1) und der folgenden Programmierung kann diese Verbindung hergestellt werden. 

![Verbindung zum ScoreKeeper](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/12.png)

### Der Scorekeeper<a name="3.4"></a>

Der ScoreKeeper reagiert auf die Nachrichten des Balls mit einer Erhöhung des Scores. Dieser wird nach der Betätigung der Act-Methode oben mittig auf dem Spielfeld angezeigt und zeigt somit den Spielern ihre aktuelle Fail-Score an. 

#### Anzeige des Scores

Um den ScoreKeeper anzuzeigen, benutzen wir einen *public void act* und *setImage*. In diesem Befehl definieren wir neben dem Namen auch die Größe sowie die Farbe. Damit zu Beginn der Score auf *0* steht, führen wir die Variable *score = 0* ein. 

![Variable und Image](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/13.png)

#### Fail-Counter und Erhöhung

Der ScoreKeeper erhält vom Ball die Nachricht mit dem Befehl *ScoreRight* oder *ScoreLeft*. Er reagiert auf diesen mit dem Befehl, den Score zu erhöhen. Dieser erhöht sich um die Zahl 1. 

![Erhöhung des Fail Scores](https://github.com/Frecca/Projektseite-Nr.-2/blob/main/14.png)

## Herausforderungen<a name="4"></a>

Die größte Herausforderung in der Programmierung bestand zunächst darin, dass wir mit Greenfoot unvertraut waren und die Einarbeitung in das Programm nicht so einfach war, was durch die Corona Situation und die damit verbundene Arbeit Zuhause erschwert wurde. Des Weiteren gab es öfter Probleme und Fehlermeldungen, deren Ursache oftmals nicht so leicht zu erkennen war und auch die Behebung dieser Fehler gestaltete sich auf Grund des neuen Programms und der mangelnden Erfahrungen schwierig. Wir mussten zunächst ein Verständnis dafür bekommen, wie die einzelnen Actor miteinander kommunizieren und welche Programmierungen für unsere Vorstellungen am Geeignetesten waren. Mit der Zeit wurde diese Herausforderung aber leichter. 

Rückblickend betrachtet sind wir, auch wenn wir öfter an Stellen nicht weiter gekommen sind und Probleme hatten, stets voran gekommen und konnten somit unser Projekt stets weiter entwickeln.

## Schlusswort<a name="5"></a>

Nun haben wir ein Jahr lang Informatikunterricht gehabt. Im ersten Halbjahr haben wir unser erste Projekt "Maze Race" mit Snap! programmiert und konnten uns langsam aber sicher in das Programm arbeiten und uns mit ein paar Informatikkenntnissen vertraut machen. 

Unser zweites Projekt haben wir dann mit Greenfoot programmiert. Auch, wenn ein Großteil der Programmierung und der Projektarbeit auf Grund von Corona stattfinden musste, haben wir nicht den Spaß am Programmieren verloren. Es war und ist schön zu sehen, wie wir uns nach und nach mit Greenfoot und der anspruchsvolleren Programierung vertraut machen konnten und jedesmal die Programmierung besser verstanden haben. 
Wir beide sind am Anfang unserer Arbeit mit Greenfoot nicht davon ausgegangen, dass wir dieses Projekt bewerkstelligen können. Aber nach der Einarbeitung und mit Hilfe des Buches sowie Herrn Buhls Tipps haben wir es letztendlich geschafft und sind sehr zufrieden mit unserem Projekt. Zwar gab es in jeder Stunde Probleme bei der Programmierung aber diese haben uns dabei geholfen, Greenfoot besser zu verstehen und wir konnten alle Probleme beheben. 

Nach einem Jahr Informatikunterricht haben wir uns gute Grundkenntnisse in den Programmen Snap! und Greenfoot aneignen können und sind stets an den Anforderungen und Problemen gewachsen. 
