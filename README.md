<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulaire de Recensement</title>
    <script src="https://cdn.emailjs.com/dist/email.min.js"></script>
    <script>
        (function () {
            // Initialisation de EmailJS avec votre User ID
            emailjs.init("VOTRE_USER_ID"); // Remplacez "VOTRE_USER_ID" par votre ID utilisateur EmailJS
        })();
    </script>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 20px;
            padding: 0;
            background-color: #f4f4f9;
        }

        form {
            background: #ffffff;
            padding: 20px;
            border-radius: 5px;
            max-width: 600px;
            margin: auto;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        h1, h2 {
            text-align: center;
        }

        label {
            font-weight: bold;
            display: block;
            margin-bottom: 5px;
        }

        input, select, textarea, button {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .radio-group {
            display: flex;
            gap: 15px;
            margin-bottom: 15px;
        }

        button {
            background-color: #5cb85c;
            color: white;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: #4cae4c;
        }
    </style>
</head>
<body>
    <h1>Formulaire de Recensement</h1>
    <form id="recensementForm">
        <h2>Informations Étudiant</h2>
        <label for="nom">Nom :</label>
        <input type="text" id="nom" name="nom" required>
        
        <label for="prenom">Prénom :</label>
        <input type="text" id="prenom" name="prenom" required>
        
        <label for="date_naissance">Date de naissance :</label>
        <input type="date" id="date_naissance" name="date_naissance" required>
        
        <label for="lieu_naissance">Lieu de naissance :</label>
        <input type="text" id="lieu_naissance" name="lieu_naissance" required>
        
        <label for="boursier">Boursier :</label>
        <select id="boursier" name="boursier">
            <option value="Oui">Oui</option>
            <option value="Non">Non</option>
        </select>
        
        <label for="filiere">Filière :</label>
        <input type="text" id="filiere" name="filiere" required>
        
        <label for="classe">Classe :</label>
        <input type="text" id="classe" name="classe" required>
        
        <label for="email">Email :</label>
        <input type="email" id="email" name="email" required>
        
        <label for="telephone">Numéro de téléphone :</label>
        <input type="tel" id="telephone" name="telephone" required>
        
        <label for="adresse">Adresse :</label>
        <input type="text" id="adresse" name="adresse" required>

        <h2>Informations Tuteurs</h2>
        <label for="nom_tuteur">Nom :</label>
        <input type="text" id="nom_tuteur" name="nom_tuteur" required>
        
        <label for="prenom_tuteur">Prénom :</label>
        <input type="text" id="prenom_tuteur" name="prenom_tuteur" required>
        
        <label for="metier_tuteur">Métier :</label>
        <input type="text" id="metier_tuteur" name="metier_tuteur" required>
        
        <label for="email_tuteur">Email :</label>
        <input type="email" id="email_tuteur" name="email_tuteur" required>
        
        <label for="telephone_tuteur">Téléphone :</label>
        <input type="tel" id="telephone_tuteur" name="telephone_tuteur" required>

        <h2>Informations Supplémentaires</h2>
        <label>Avez-vous des antécédents médicaux importants que nous devrions connaître ?</label>
        <div class="radio-group">
            <label><input type="radio" name="antecedents_med" value="Oui" required> Oui</label>
            <label><input type="radio" name="antecedents_med" value="Non" required> Non</label>
        </div>
        <label for="details_antecedents">Si oui, lesquels ?</label>
        <textarea id="details_antecedents" name="details_antecedents" placeholder="Décrivez ici si nécessaire..."></textarea>

        <label>Vivez-vous seul ?</label>
        <div class="radio-group">
            <label><input type="radio" name="vivre_seul" value="Oui" required> Oui</label>
            <label><input type="radio" name="vivre_seul" value="Non" required> Non</label>
        </div>
        <label for="raison_vivre_seul">Si oui, pour quelles raisons ?</label>
        <textarea id="raison_vivre_seul" name="raison_vivre_seul" placeholder="Expliquez ici si nécessaire..."></textarea>

        <label>Quelles activités ou événements souhaiteriez-vous que le Bureau des Étudiants organise ?</label>
        <textarea id="activites" name="activites" placeholder="Proposez vos idées ici..."></textarea>
        </div>
        <label>Avez-vous une activité génératrice de revenu que vous exercez?</label>
        <textarea id="activites" name="activites" placeholder="Proposez vos idées ici..."></textarea>

        <button type="submit">Envoyer</button>
    </form>

    <script>
        // Gestion de l'envoi via EmailJS
        document.getElementById('recensementForm').addEventListener('submit', function (event) {
            event.preventDefault(); // Empêche le rechargement de la page

            // Envoi des données à EmailJS
            emailjs.sendForm('VOTRE_SERVICE_ID', 'VOTRE_TEMPLATE_ID', this) // Remplacez VOTRE_SERVICE_ID et VOTRE_TEMPLATE_ID
                .then(function () {
                    alert('Formulaire envoyé avec succès !');
                }, function (error) {
                    alert('Erreur lors de l\'envoi : ' + JSON.stringify(error));
                });
        });
    </script>
</body>
</html>
