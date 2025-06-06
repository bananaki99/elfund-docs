΄Ελεγχος Στοιχείων Βάσης
========================

Έλεγχος καθαρής θέσης (NET_ASSET)
---------------------------------

Ελέγχεται ότι το άθροισμα του γινόμενου της λογιστικής τιμής επί τον αριθμό
μετοχών/μεριδίων για κάθε είδος μετοχής/μεριδίου του ΕΟ ισούται με την αξία του
ενεργητικού μείον την αξία του παθητικού. 

Πιο αναλυτικά θα πρέπει να ισχύει η παρακάτω σχέση: 

.. math::

    \mathrm{LHS} &= \mathrm{RHS}

    \mathrm{LHS} &= \sum_s(\mathrm{AGG.BK\_PRC}\sum_h\mathrm{HLDR.QNTTY})

    \mathrm{RHS} &= \mathrm{ASSETS} - \mathrm{LIABILITIES}

    \mathrm{ASSETS} &= \sum_i\mathrm{DPST.STCK} + \sum_iA\mathrm{SST\_DBT.STCK}  + \sum_i\mathrm{ASST\_LN.STCK} + \sum_i\mathrm{SHR.STCK} + \sum_i\mathrm{DER.STCK} + \sum_i\mathrm{ASST\_NN\_FNNCL.STCK} + \sum_i\mathrm{ASST\_RMNNG.STCK}

    \mathrm{LIABILITIES} &= \sum_i\mathrm{LBLTY\_DBT.STCK} + \sum_i\mathrm{LBLTY\_LN.STCK} + \sum_i\mathrm{LBLTY\_RMNNG.STCK}

    s &= \text{Άθροισμα ανά μετοχή, μερίδιο, κατηγορία μεριδίου του επενδυτικού οργανισμού}

    h &= \text{Άθροισμα ανά κάτοχο}

    i &= \text{Άθροισμα ανά στοιχείο του λογαριασμού του ισολογισμού που ακολουθεί}

Σε περίπτωση που δεν ισχύει η παραπάνω σχέση θα παρέχονται οι παρακάτω τιμές:

    ID 
        Αναγνωριστικός κωδικός ΕΟ

    DATE
        Ημερομηνία

    LHS
        H τιμή του LHS

    RHS
        Η τιμή του RHS

    ASSETS
        Η αξία του ενεργητικού

    LIABILITIES
        Η αξία του παθητικού

    DIFFERENCE
        H διαφορά LHS - RHS 



Έλεγχος μεταξύ εισοδήματος και ροών (INCOME_CROSSCHECK)
-------------------------------------------------------

Ελέγχεται ότι το συνολικό εισόδημα για κάθε ΕΟ ισούται με το υπολογιζόμενο
εισόδημα με βάση τις συναλλαγές στο ενεργητικό, παθητικό καθώς και τις
συμμετοχές και εξοφλήσεις. 

Πιο αναλυτικά θα πρέπει να ισχύει η παρακάτω σχέση: 

.. math::

    \mathrm{LHS} &= \mathrm{RHS}

    \mathrm{LHS} &= (\mathrm{ASSET\_FLOWS} - \mathrm{LIABILITY\_FLOWS}) - (\mathrm{SUBSCRIPTIONS} - \mathrm{REDEMPTIONS})

    \mathrm{RHS} &= \sum_s(\mathrm{AGG.INCM}\sum_h\mathrm{HLDR.QNTTY})

    \mathrm{SUBSCRIPTIONS} &= \sum_s\sum_h\mathrm{HLDR.SBSCRPTNS}

    \mathrm{REDEMPTIONS} &= \sum_s\sum_h\mathrm{HLDR.RDMPTNS}

    \mathrm{ASSET\_FLOWS} &= \sum_i\mathrm{DPST.FLS} + \sum_iA\mathrm{SST\_DBT.FLS}  + \sum_i\mathrm{ASST\_LN.FLS} + \sum_i\mathrm{SHR.FLS} + \sum_i\mathrm{DER.FLS} + \sum_i\mathrm{ASST\_NN\_FNNCL.FLS} + \sum_i\mathrm{ASST\_RMNNG.FLS}

    \mathrm{LIABILITY\_FLOWS} &= \sum_i\mathrm{LBLTY\_DBT.FLS} + \sum_i\mathrm{LBLTY\_LN.FLS} + \sum_i\mathrm{LBLTY\_RMNNG.FLS}

    s &= \text{Άθροισμα ανά μετοχή, μερίδιο, κατηγορία μεριδίου του επενδυτικού οργανισμού}

    h &= \text{Άθροισμα ανά κάτοχο}

    i &= \text{Άθροισμα ανά στοιχείο του λογαριασμού του ισολογισμού}

Σε περίπτωση που δεν ισχύει ο έλεγχος θα παρέχονται οι παρακάτω τιμές:

    ID 
        Αναγνωριστικός κωδικός ΕΟ

    DATE
        Ημερομηνία αναφοράς

    PERIOD
        Περίοδος αναφοράς

    LHS
        H τιμή του LHS

    RHS
        Η τιμή του RHS

    Εισροές
        Η τιμή των εισροών

    Εκροές
        Η τιμή των εκροών

    Συνναλαγές Ενεργητικού
        Η τιμή των συναλλαγών στο ενεργητικού

    Συνναλαγές Παθητικού 
        Η τιμή των συναλλαγών στο παθητικό

    DIFFERENCE
        LHS - RHS

   
Έλεγχος δεδουλευμένων τόκων (ACCRLS)
------------------------------------
Ελέγχεται ότι το άθροισμα των δεδουλευμένω τόκων και μισθωμάτων ισούται με το
αντίστοιχο ποσό από τα λοιπά στοιχεία ενεργητικού.

Πιο αναλυτικά θα πρέπει να ισχύει η παρακάτω σχέση: 

.. math::

    \mathrm{LHS} &= \mathrm{RHS}

    \mathrm{LHS} &=  \sum_i\mathrm{DPST.ACCRLS} + \sum_i\mathrm{ASST\_DBT.ACCRLS} + \sum_i\mathrm{ASST\_LN.ACCRLS} + \sum_i\mathrm{ASST\_NN\_FNNCL.ACCRLS} 

    \mathrm{RHS} &= \mathrm{ASST\_RMNNG.AI_DPST.STCK} + \mathrm{ASST\_RMNNG.AI_DBT.STCK} + \mathrm{ASST\_RMNNG.AI_LN.STCK} + \mathrm{ASST\_RMNNG.AR.STCK}

    i &= \text{Άθροισμα ανά στοιχείο του λογαριασμού του ισολογισμού που ακολουθεί}

Σε περίπτωση που δεν ισχύει η παραπάνω σχέση θα παρέχονται οι παρακάτω τιμές:

    ID 
        Αναγνωριστικός κωδικός ΕΟ

    DATE
        Ημερομηνία αναφοράς

    LHS
        H τιμή του LHS

    RHS
        Η τιμή του RHS

    DIFFERENCE
        Η διαφορά LHS - RHS
