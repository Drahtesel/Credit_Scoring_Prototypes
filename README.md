# Credit_Scoring_Prototypes

Die Implementierung wurde auf drei Notebooks aufgeteilt:

  1. Datenvorbereitung
  2. Optimierung
  3. Modellvergleich

Ziel des Projekts ist die systematische Entwicklung, Optimierung und Bewertung mehrerer Credit-Scoring-Modelle auf Basis des German Credit Data Sets. 
Der Fokus liegt dabei auf reproduzierbarer Modellleistung, fairen Vergleichen sowie Modellinterpretierbarkeit.

**1. Datenvorbereitung**
   
      Im ersten Schritt wird der Rohdatensatz aus dem UCI Machine Learning Repository vollständig aufbereitet.
      Inhalte dieses Notebook:
      
        - Laden und Strukturierung des German Credit Data Sets
        - Semantische Umbenennung aller Attribute
        - Übersetzung der kategorialen Codes in Klartext
        - One-Hot-Encoding kategorialer Merkmale
        - Min-Max-Skalierung numerischer Variablen
        - Rekodierung der Zielvariable (0 = guter, 1 = schlechter Kredit)
        - Feature Selection mittels Chi²-Test
      
      Ergebnis dieses Schrittes sind mehrere CSV-Datensätze, die als Datenbasis für alle weiteren Analysen dienen.

**2. Optimierung**

      Im zweiten Schritt erfolgt die Hyperparameteroptimierung verschiedener Modellklassen mittels Bayesian Optimization.
      Optimierte Modelle:
   
          - Logistische Regression
          - Random Forest
          - XGBoost 
          - Neuronales Netz

      Inhalte dieses Notebook:
   
          - Optimierung der Modelle mithilfe von Bayesian Optimization
          - Training aller Optimierungsiterationen
          - Analyse unterschiedlicher Feature-Selection-Stufen
          - Untersuchung des Einflusses der Trainingsdatenmenge
          - Erfassung von Laufzeiten und Konvergenzverhalten

      Dieser Schritt liefert die optimalen Hyperparameter für das finale Training.

**3. Training**

     Im finalen Schritt werden die Modelle mit den optimierten Hyperparametern trainiert und umfassend evaluiert.
     Inhalte dieses Notebook:

         - Wiederholte, stratifizierte Cross-Validation (10×10)
         - Bewertung mit mehreren Metriken (AUC, Accuracy, LogLoss)
         - Kostenbasierte Bewertung (asymmetrische Fehlkosten)
         - ROC-Kurven mit Konfidenzintervallen
   
     Zusätzlich wird die Erklärbarkeit der Modelle analysiert:
  
         - Intrinsisch (Logistische Regression)
         - Globale Erklärung mittels SHAP
         - Lokal mittels LIME (instanzbasiert)

Alle Visualisierungen werden automatisiert gespeichert und dienen der Ergebnisinterpretation.
