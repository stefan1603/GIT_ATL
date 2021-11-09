

#  AT - Labor
## Use Case Gerald
#
#
#
#### Aufgabenstellung
Die Aufgabe war es, technische Lösungen für die Wünsche von Gerald unter Einbeziehung der gewählten Räume zu entwickeln bzw. anzuwenden. 
Der gewählte Raum ist das Schlafzimmer. 

#### Kurzbeschreibung Klient: Gerald
Gerald hat eine starke körperliche Einschränkung und eine Hörbeeinträchtigung. Er ist auf Pflege angewiesen und kann
Klänge wahrnehmen. Er würde gerne eine gewisse Autonomie zurückerlangen und seine Umgebung (z.B. Licht, Jalousien,
Musik) steuern können. Darüberhinaus würde er gerne Klänge/Visuals erzeugen können und sich die Zeit mit
Computerspielen vertreiben. Er möchte gerne im Internet surfen oder am Smartphone mit seinen Freunden kommunizieren
können.

#### Lösungsansätze
    
    - AsTeRICs Grid
    - IRTrans
    - Eingabegerät FABI
    - Eingabegerät Tobi
    - Betriebsystemeinstellungen für Accessibility
    
# AsTeRICs Grid
Asterics Grid ist eine freie Software für ACC-Anwendungen. Durch dieses webbasierte Tool ist es möglich,  Klientenspezifische Lösungen zu kreiren und dadurch den Lebensstandard von Personen mit gewissen Einschränkungen zu erhöhen. Im Zusammenspiel mit dem AsTeRICS Framework kann die Realisierung zusätzlicher Funktionalitäten wie Umgebungs- oder Computersteuerung ermöglicht werden.  
In diesem Grid-Layout kann man verschiedene und verschieden-viele Elemente hinzufügen. Das Homegrid für den Klienten Gerald hat die wichtigsten Funktionen, wie z.B. Licht und Heizungssteuerung. Weiters kann er den Fernseher bedienen und eine Visual-Smart-Glühbirne steuern. 


<p align="center">
<img src="Pics/grid.jpg" width="800" height="450">
</p>


Die einzelnen Elemente können individuell eingestellt werden und mit der ACS (Asterics Configuration Suite) kommunizieren. Jedem Element kann eine oder mehrere Aktionen hinzugefügt werden. Für die meisten Elemente wurde eine eigene Asterics-Aktion ausgewählt, welche mit der ACS ausgeführt werden kann. 

<p align="center">
<img src="Pics/konfig_licht_AN.jpg" width"800" height="450">
</p>




    
Um die physischen Umgebungselemente wie Licht, Jalousie, Temperatur, usw. anzusteuern, braucht man ein Tool, welches eine Haussteuerung anbietet. Es wurde das Programm OPENHAB herangezogen, weil es zu diesem Tool ein fertiges Asterics-Plugin gibt. 

<p align="center">
<img src="Pics/openhab.jpg" width"600" height="350">
</p>

    
In openhab kann man seine eigene Homesteuerungswebseite desigen und die entsprechenden Geräte konfigurieren. Für unsere Anwendung wurde das vorgegeben. Als Beispielwebseite ist folgende gezeigt:

<p align="center">
<img src="Pics/openhab_beispiel_ui.jpg" width"800" height="250">
</p>

    
Wichtig für die Konfiguration ist die richtige IP-Adresse (oder URL). Diese ist unter dem Hostnamen einzutragen. Wenn man auf dem eigenen Rechner bleiben möchte muss man "localhost" eingeben. Ansonsten ist im Living-Lab die URL fhtw-building-control.technikum-wien.at anzugeben. 

Um den Wünschen des Klienten gerecht zu werden, musste die Steuerung des Fernsehers und die der Visual-Glühlampe anwendungsfreundlicher gemacht werden. Dies wurde mit der IRTrans-Komponente realisiert.  Dies ist ein Gerät, welches Infrarot-Befehle "erlernen" kann und so das Senden/Empfangen von IR-Signalen ausführt. 

<p align="center">
<img src="Pics/irtrans_gehause.jpg" width"600" height="400">
</p>

<p align="center">
<img src="Pics/befehl_lernen_irtrans.jpg" width"400" height="550">
</p>

    
Weiters macht das Plugin "IRTrans" in der ACS das Kommunizieren mit dem Grid wesentlich leichter/schneller. 

<p align="center">
<img src="Pics/irtrans_plugin.jpg" width"400" height="550">
</p>


In diesem Plugin trägt man die eingelernten Befehle, sowie den Namen der Funktion ein. In diesem Zusammenhang heißt die Funktion (Fernbedienung) "toshiba" und es gibt 18 Arten den Fernseher zu bedienen. 

<p align="center">
<img src="Pics/properties_irtrans.jpg" width"700" height="650">
</p>
 


Dieser Befehlsnamen bzw. der dazugehörige String muss dann im Asterics-Grid für das richtige Element eingetragen werden.

<p align="center">
<img src="Pics/fernseher_grid.jpg" width"800" height="450">
</p>

<p align="center">
<img src="Pics/konifg_fernseher_AnAus.jpg" width"700" height="650">
</p>
    
    
Um die UX (User Experience) und Anwendungsfreundlichkeit des ganzen Systems zu testen wurde der FittsTask angewandt. Dieses liegt dem allgemeinen Fitt's Law zugrunde. Es ist ein prädiktives Modell, welches die Dauer für menschliche Bewegungen bei Zeigeaufgaben vorhersagt bzw. auswerten lässt. Dabei verwendet es die Distanz zum Ziel, sowie dessen Größe als Parameter
Bei dem Versuch wurde drei verschiedene Arten verwendet um sich durch das UI zu navigieren. 

    - MouseButton
    - Dwelling Methode
    - Keyboard/Fabi-Button
        

### MouseButton

<p align="center">
<img src="Fotos_FittsTask/CameraMouse_mousebutton.jpg" width"300" height="200">
</p>

### Dwelling Methode

<p align="center">
<img src="Fotos_FittsTask/CameraMouse_dwell.jpg" width"300" height="200">
</p>


### Keyborad/Fabi-Button
<p align="center">
<img src="Fotos_FittsTask/CamerMouse_Button_FABI.jpg" width"300" height="200">
</p>


Wie man eindeutig sieht hat die Dwelling-Methode einen wesentlich höheren TP und die am anwendungsfreundlichste Methode ist. Die anderen beiden Methoden sind hier fast ident. 
Bei der durchschnitllichen Dauer zur Erfüllung einer Bewegung, kurz MP, schneidet auch die Dwelling-Methode am Besten ab. 


# Eingabegerät FABI

## 1. BESCHREIBUNG
FABI - Flexible Assistive Button Interface, hat bis 9 externe Tasten und kann auf Windows-PC, Mac-Computer, 
Tablet oder Smartphone per USB-Anschluss verwendet werden.
Mit dem FABI sind Computerspiele, im Internet zu Surfen, E-mails schreiben und vieles mehr möglich. 
(file:///C:/Users/Dana/Downloads/FABI_UserManual.pdf)

## 2. DIE KONFIGURATION
<p align="center">
<img src="Pics/fabi_konf.jpg" width"500" height="450">
</p>


### 2.1. Auf den Online Seite würde die Buttons konfiguriert
(https://asterics.github.io/Addon-Bluetooth-WebGUI/webgui/index_fabi.htm#tabActions)

Button1 wurde erstellt als KEY_RIGHT um im Asterics Grid nach recht navigieren zu können, 
und der Button2 als KEY_SPACE, damit ist die normale Leertaste möglich bzw. einen Befehl im Asterics-Grid auszuwählen. 

<p align="center">
<img src="Pics/button_1.jpg" width"500" height="450">
</p>

<p align="center">
<img src="Pics/button_2.jpg" width"500" height="450">
</p>



### 2.2. In Asterics Grid würde auch bei Eingabeoption, für das Fabi konfiguerieren mussen.
Asterics -> Eingabeoption-> Sequentielle Eingabe

<p align="center">
<img src="Pics/eingabe_opt.jpg" width"500" height="450">
</p>

## 3. DIE VERWENDUNG 
Da der Klient nur die große Zehe bewegen und den rechten Arm leicht heben/senken kann, hat man zwei Knöpfe genommen.
Der blaue Knopf(Button1) wurde gedacht um nach rechts navigieren zu können(evtl. mit der Zehe).  
Der rote Knopf(Button2) wurde gedacht um "Space" nutzen zu können (evtl. rechter Arm).

