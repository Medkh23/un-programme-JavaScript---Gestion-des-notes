# un-programme-JavaScript---Gestion-des-notes

<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title></title>
</head>
<body>
    <h2>Gestion de notes</h2>
    <script>    
     //La declaration du tableau
        var taille = 3;
        var tabNotes = new Array(taille);
     //La lecture des notes de chaque étudiant
        for (var index = 0; index < taille; index++) {
            var nom_Etudiant = prompt("Donner le nom de l'étudiant : ");
            var note_Lab = Number.parseInt(prompt("Donner la note du laboratoire : ", 0));
            var note_Intra = Number.parseInt(prompt("Donner la note du l'examen intra : ", 0));
            var note_Final = Number.parseInt(prompt("Donner la note du l'examen final : ", 0));
     //Stocker les 3 notes dans le tableau tabNotes
            tabNotes[index] = new Array(nom_Etudiant, note_Lab, note_Intra, note_Final);
        }
    //La boucle du calcule de la moyenne de chaque étudiant
        for (var element of tabNotes) {
            var moyenne = 0;
            var nomEtudcourant = element.shift();
            for (var note of element) {
                moyenne = moyenne + note;
            }
            moyenne = moyenne / element.length;

            //Vérifier si l'étudiant courant a le droit a une reprise
            if (moyenne >= 60 ) {
                document.writeln("L'étudiant " + nomEtudcourant + " a réussi le cours : " + moyenne.toFixed(2) + "<br>");

            } else if (moyenne >= 54 && moyenne <= 59 && element[2] >= 60) {
                document.writeln("L'étudiant " + nomEtudcourant + " a le droit a une reprise : " + moyenne.toFixed(2) + "<br>");

            } else {
                document.writeln("L'étudiant " + nomEtudcourant + " a échoué le cours : " + moyenne.toFixed(2) + "<br>");
            }// toFixed(2) arrondie a 2 chiffre aprés la virgule

        }
    





    </script>

</body>
</html>
