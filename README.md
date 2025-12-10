# Antrenarea Retelelor Neuronale folosind Controlul Congestiei (AIMD)


## 1. Descrierea Proiectului
Acest proiect isi propune sa testeze o ipoteza inedita: aplicarea algoritmului **AIMD (Additive Increase Multiplicative Decrease)** in antrenarea retelelor neuronale.

Algoritmul AIMD este faimos pentru rolul sau in stabilitatea internetului (protocolul TCP). Ideea noastra este sa adaptam acest mecanism "arheologic" (din 1989) pentru a ajusta dinamic **Rata de Invatare (Learning Rate)** a unui model AI modern. Consideram cresterea erorii (loss) ca fiind o "congestie", declansand o scadere brusca a vitezei de invatare.

## 2. Datele Folosite (EDA)
Utilizam setul de date **CIFAR-10**, un benchmark standard in Computer Vision.
* **Continut:** 60.000 de imagini color (32x32 pixeli).
* **Clase:** 10 clase echilibrate (avion, masina, pasare, pisica, etc.).

Mai jos sunt cateva exemple din setul de date pe care l-am analizat:
<img width="787" height="100" alt="img1" src="https://github.com/user-attachments/assets/b6277391-8d94-4ac9-ab1a-e888165473ef" />


## 3. Modelul si Implementarea
Pentru a avea un termen de comparatie valid, am implementat un model **Baseline** (de baza):
* **Arhitectura:** CNN (Convolutional Neural Network) cu 3 straturi convolutionale.
* **Mediu de lucru:** Google Colab (T4 GPU).
* **Fisiere:** Codul sursa se gaseste in fisierul `Project_ASI.ipynb`.

## 4. Rezultate Intermediare (Baseline)
In aceasta etapa, am antrenat modelul standard (fara AIMD) pentru a stabili linia de baza.
Dupa cum se observa in graficele de mai jos, modelul converge corect, atingand o acuratete de peste 70% in primele 10 epoci:

<img width="1003" height="389" alt="img2" src="https://github.com/user-attachments/assets/201483c0-56f6-4531-8be6-9a18b364d6bf" />


## 5. Plan de Lucru (Next Steps)
1.  Implementarea clasei `AimdScheduler` in Keras/TensorFlow.
2.  Rularea experimentelor comparative: Baseline vs. AIMD.
3.  Analiza stabilitatii si vitezei de convergenta.
