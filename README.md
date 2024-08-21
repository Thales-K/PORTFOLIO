# PORTFOLIO
Bienvenue sur mon portfolio GitHub ! Je suis un Analyste de Données avec 7 ans d'expérience en statistiques, analyse de données et visualisation. Mon expertise réside dans l'extraction d'informations significatives à partir de données pour soutenir les processus de prise de décision et offrir des solutions pertinentes. Je suis passionné par l'apprentissage continu et j'aime travailler sur des projets stimulants qui repoussent les limites de mes compétences.

## À propos de moi

Nom : Thalès KIKI

Langues : Français (Avancé), Anglais (Intermédiaire)

Langages de programmation : Python (Intermédiaire), SQL (Avancé), DAX (Intermédiaire), M Query (Intermédiaire)

Compétences en logiciels : Microsoft Excel (Power Query, Power Pivot, Tableaux Croisés Dynamiques), Microsoft Power BI, Stata, SPSS, 

Suite Microsoft Office (Word, PowerPoint, Outlook)

Compétences principales : Visualisation de données, Processus ETL, Modélisation de données, Analyse exploratoire des données, Apprentissage automatique

Qualités : Esprit analytique et synthétique, Communication, Travail en équipe


## Expérience Professionnelle

    Statisticien Économiste 
    Institut National de la Statistique et de la Démographie (INStaD) - Bénin
    Juillet 2019 - Septembre 2023

    Statisticien Économiste 
    Direction Générale de l'Économie (DGE) - Bénin
    Octobre 2016 - Mars 2019



## Éducation & Certifications
    
    Microsoft Certified: Power BI Data Analyst Associate (Juillet 2024) 
   
    Power BI Data Analyst Professional Certificate (Mars 2024 - Mai 2024)
    Microsoft (Coursera) - Cours en ligne

    Diplôme d’Ingénieur Statisticien Économiste (2013 - 2016)
    École Nationale de la Statistique et de l’Analyse Économique (ENSAE), Dakar (Sénégal) - Présentiel
    
    Diplôme de Technicien Supérieur en Statistique (2009 - 2012)
    École Nationale d’Économie Appliquée et de Management (ENEAM), Cotonou (Bénin) - Présentiel


## Projets

Ici, je présente certains des projets d'analyse de données sur lesquels j'ai travaillé. Ces projets mettent en avant mes compétences en extraction, nettoyage, analyse et visualisation de données. N'hésitez pas à explorer les dépôts ci-dessous :

[Projet 1 : Enquête sur les Professionnels de la Donnée](https://github.com/Thales-K/PORTFOLIO/blob/main/assets/Rapport/PROJET%20-%20LES%20PROFESSIONNELS%20DE%20LA%20DONNEE.pbix)

Ce projet utilise les données d'une enquête qui vise à comprendre les préférences, les tendances et les défis auxquels les professionnels des données sont confrontés. Il offre une interface conviviale avec des visualisations interactives pour faciliter l'exploration des données et la prise de décision. Cette base de données est disponible [ici](https://www.kaggle.com/datasets/ahmedmohamedibrahim1/data-professional-survey-breakdown)  

Il est réalisé avec Power bi desktop. Les données ont été nettoyées et transformées avec Power Query grâce au code suivant : 
	let
	    Source = Excel.Workbook(File.Contents("C:\Users\USER\Desktop\Thales-K\PORTFOLIO\Power BI Project.xlsx"), null, true),
	    #"Data Professional Survey_Sheet" = Source{[Item="Data Professional Survey",Kind="Sheet"]}[Data],
	    #"Promoted Headers" = Table.PromoteHeaders(#"Data Professional Survey_Sheet", [PromoteAllScalars=true]),
	    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"Identifiant", type text}, {"Email", type text}, {"Date d'interview (America/New_York)", type date}, {"Heure  d'interview  (America/New_York)", type time}, {"Naviagteur", type text}, {"Système", type text}, {"Ville", type text}, {"Pays", type text}, {"Référant", type text}, {"Durée de l'interview", type duration}, {"Q1 - Position Actuel", type text}, {"Q2 - Avez changé de carrière?", type text}, {"Q3 - Salaire actuel (en USD)", type text}, {"Q4 - Industrie?", type text}, {"Q5 - Langage de Programmation préféré", type text}, {"Q6 - A quel point Etes vous satisfait de votre salaire? ", Int64.Type}, {"Q6 - A quel point Etes vous satisfait de votre équilibre viepriéé/vie professionnel? ", Int64.Type}, {"Q6 - A quel point Etes vous satisfait de vos collègues? ", Int64.Type}, {"Q6 - A quel point Etes vous satisfait de votre hiérarchie? ", Int64.Type}, {"Q6 - A quel point Etes vous satisfait de votre avancement? ", Int64.Type}, {"Q6 - A quel point Etes vous satisfait du fait d'apprendre de nouvelles choses? ", Int64.Type}, {"Q7 -A quel point il a été difficile de vous orienter vers la Data?", type text}, {"Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité?", type text}, {"Q9 - Masculin/Féminin ?", type text}, {"Q10 - Age", Int64.Type}, {"Q11 - Dans quel pays habité vous?", type text}, {"Q12 -Niveau d'éducation ", type text}, {"Q13 - Ethnie", type text}}),
	    #"Split Column by Delimiter" = Table.SplitColumn(#"Changed Type", "Q1 - Position Actuel", Splitter.SplitTextByDelimiter(" (Please Specify)", QuoteStyle.Csv), {"Q1 - Position Actuel.1", "Q1 - Position Actuel.2"}),
	    #"Changed Type1" = Table.TransformColumnTypes(#"Split Column by Delimiter",{{"Q1 - Position Actuel.1", type text}, {"Q1 - Position Actuel.2", type text}}),
	    #"Renamed Columns" = Table.RenameColumns(#"Changed Type1",{{"Q1 - Position Actuel.1", "Q1 - Position Actuel"}, {"Q1 - Position Actuel.2", "Q1 - Position Actuel (Précision)"}}),
	    #"Replaced Value" = Table.ReplaceValue(#"Renamed Columns",":","",Replacer.ReplaceText,{"Q1 - Position Actuel (Précision)"}),
	    #"Replaced Value1" = Table.ReplaceValue(#"Replaced Value","","Non déclaré",Replacer.ReplaceValue,{"Q1 - Position Actuel (Précision)"}),
	    #"Split Column by Delimiter1" = Table.SplitColumn(#"Replaced Value1", "Q4 - Industrie?", Splitter.SplitTextByDelimiter(" (Please Specify)", QuoteStyle.Csv), {"Q4 - Industrie?.1", "Q4 - Industrie?.2"}),
	    #"Changed Type2" = Table.TransformColumnTypes(#"Split Column by Delimiter1",{{"Q4 - Industrie?.1", type text}, {"Q4 - Industrie?.2", type text}}),
	    #"Renamed Columns1" = Table.RenameColumns(#"Changed Type2",{{"Q4 - Industrie?.1", "Q4 - Industrie?"}, {"Q4 - Industrie?.2", "Q4 - Industrie? Précision"}}),
	    #"Replaced Value2" = Table.ReplaceValue(#"Renamed Columns1",":","",Replacer.ReplaceText,{"Q4 - Industrie? Précision"}),
	    #"Replaced Value3" = Table.ReplaceValue(#"Replaced Value2","","Non déclaré",Replacer.ReplaceValue,{"Q4 - Industrie? Précision"}),
	    #"Split Column by Delimiter2" = Table.SplitColumn(#"Replaced Value3", "Q5 - Langage de Programmation préféré", Splitter.SplitTextByDelimiter(":", QuoteStyle.Csv), {"Q5 - Langage de Programmation préféré.1", "Q5 - Langage de Programmation préféré.2"}),
	    #"Changed Type3" = Table.TransformColumnTypes(#"Split Column by Delimiter2",{{"Q5 - Langage de Programmation préféré.1", type text}, {"Q5 - Langage de Programmation préféré.2", type text}}),
	    #"Renamed Columns2" = Table.RenameColumns(#"Changed Type3",{{"Q5 - Langage de Programmation préféré.1", "Q5 - Langage de Programmation préféré"}, {"Q5 - Langage de Programmation préféré.2", "Q5 - Langage de Programmation préféré (Précision)"}}),
	    #"Replaced Value5" = Table.ReplaceValue(#"Renamed Columns2","","Non déclaré",Replacer.ReplaceValue,{"Q5 - Langage de Programmation préféré (Précision)"}),
	    #"Split Column by Delimiter3" = Table.SplitColumn(#"Replaced Value5", "Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité?", Splitter.SplitTextByDelimiter(" (Please Specify):", QuoteStyle.Csv), {"Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité?.1", "Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité?.2"}),
	    #"Changed Type4" = Table.TransformColumnTypes(#"Split Column by Delimiter3",{{"Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité?.1", type text}, {"Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité?.2", type text}}),
	    #"Renamed Columns3" = Table.RenameColumns(#"Changed Type4",{{"Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité?.1", "Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité?"}, {"Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité?.2", "Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité? (Précision)"}}),
	    #"Split Column by Delimiter4" = Table.SplitColumn(#"Renamed Columns3", "Q11 - Dans quel pays habité vous?", Splitter.SplitTextByDelimiter(" (Please Specify)", QuoteStyle.Csv), {"Q11 - Dans quel pays habité vous?.1", "Q11 - Dans quel pays habité vous?.2"}),
	    #"Changed Type5" = Table.TransformColumnTypes(#"Split Column by Delimiter4",{{"Q11 - Dans quel pays habité vous?.1", type text}, {"Q11 - Dans quel pays habité vous?.2", type text}}),
	    #"Renamed Columns4" = Table.RenameColumns(#"Changed Type5",{{"Q11 - Dans quel pays habité vous?.1", "Q11 - Dans quel pays habité vous?"}, {"Q11 - Dans quel pays habité vous?.2", "Q11 - Dans quel pays habité vous? (Précision)"}}),
	    #"Replaced Value6" = Table.ReplaceValue(#"Renamed Columns4",":","",Replacer.ReplaceText,{"Q11 - Dans quel pays habité vous? (Précision)"}),
	    #"Replaced Value7" = Table.ReplaceValue(#"Replaced Value6","","Non déclaré",Replacer.ReplaceValue,{"Q11 - Dans quel pays habité vous? (Précision)"}),
	    #"Split Column by Delimiter5" = Table.SplitColumn(#"Replaced Value7", "Q13 - Ethnie", Splitter.SplitTextByDelimiter(" (Please Specify):", QuoteStyle.Csv), {"Q13 - Ethnie.1", "Q13 - Ethnie.2"}),
	    #"Changed Type6" = Table.TransformColumnTypes(#"Split Column by Delimiter5",{{"Q13 - Ethnie.1", type text}, {"Q13 - Ethnie.2", type text}}),
	    #"Renamed Columns5" = Table.RenameColumns(#"Changed Type6",{{"Q13 - Ethnie.1", "Q13 - Ethnie"}, {"Q13 - Ethnie.2", "Q13 - Ethnie (Précision)"}}),
	    #"Replaced Value8" = Table.ReplaceValue(#"Renamed Columns5",":","",Replacer.ReplaceText,{"Q13 - Ethnie (Précision)"}),
	    #"Replaced Value9" = Table.ReplaceValue(#"Replaced Value8","","Non déclaré",Replacer.ReplaceValue,{"Q13 - Ethnie (Précision)"}),
	    #"Trimmed Text" = Table.TransformColumns(#"Replaced Value9",{{"Q1 - Position Actuel (Précision)", Text.Trim, type text}, {"Q4 - Industrie? Précision", Text.Trim, type text}, {"Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité? (Précision)", Text.Trim, type text}, {"Q11 - Dans quel pays habité vous? (Précision)", Text.Trim, type text}, {"Q13 - Ethnie (Précision)", Text.Trim, type text}}),
	    #"Lowercased Text" = Table.TransformColumns(#"Trimmed Text",{{"Q1 - Position Actuel (Précision)", Text.Lower, type text}, {"Q4 - Industrie? Précision", Text.Lower, type text}, {"Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité? (Précision)", Text.Lower, type text}, {"Q11 - Dans quel pays habité vous? (Précision)", Text.Lower, type text}, {"Q13 - Ethnie (Précision)", Text.Lower, type text}}),
	    #"Duplicated Column" = Table.DuplicateColumn(#"Lowercased Text", "Q3 - Salaire actuel (en USD)", "Q3 - Salaire actuel (en USD) - Copy"),
	    #"Split Column by Character Transition" = Table.SplitColumn(#"Duplicated Column", "Q3 - Salaire actuel (en USD) - Copy", Splitter.SplitTextByCharacterTransition({"0".."9"}, (c) => not List.Contains({"0".."9"}, c)), {"Q3 - Salaire actuel (en USD) - Copy.1", "Q3 - Salaire actuel (en USD) - Copy.2", "Q3 - Salaire actuel (en USD) - Copy.3"}),
	    #"Split Column by Character Transition1" = Table.SplitColumn(#"Split Column by Character Transition", "Q3 - Salaire actuel (en USD) - Copy.2", Splitter.SplitTextByCharacterTransition((c) => not List.Contains({"0".."9"}, c), {"0".."9"}), {"Q3 - Salaire actuel (en USD) - Copy.2.1", "Q3 - Salaire actuel (en USD) - Copy.2.2"}),
	    #"Removed Columns" = Table.RemoveColumns(#"Split Column by Character Transition1",{"Q3 - Salaire actuel (en USD) - Copy.2.1", "Q3 - Salaire actuel (en USD) - Copy.3"}),
	    #"Changed Type7" = Table.TransformColumnTypes(#"Removed Columns",{{"Q3 - Salaire actuel (en USD) - Copy.1", Int64.Type}, {"Q3 - Salaire actuel (en USD) - Copy.2.2", Int64.Type}}),
	    #"Added Custom" = Table.AddColumn(#"Changed Type7", "Salaire Moyen", each List.Average({[#"Q3 - Salaire actuel (en USD) - Copy.1"] ,[#"Q3 - Salaire actuel (en USD) - Copy.2.2"]})),
	    #"Colonne multipliée" = Table.TransformColumns(#"Added Custom", {{"Salaire Moyen", each _ * 1000, type number}}),
	    #"Removed Columns1" = Table.RemoveColumns(#"Colonne multipliée",{"Q3 - Salaire actuel (en USD) - Copy.1", "Q3 - Salaire actuel (en USD) - Copy.2.2"}),
	    #"Removed Other Columns" = Table.SelectColumns(#"Removed Columns1",{"Identifiant", "Email", "Date d'interview (America/New_York)", "Heure  d'interview  (America/New_York)", "Durée de l'interview", "Q1 - Position Actuel", "Q2 - Avez changé de carrière?", "Q3 - Salaire actuel (en USD)", "Q4 - Industrie?", "Q5 - Langage de Programmation préféré", "Q6 - A quel point Etes vous satisfait de votre salaire? ", "Q6 - A quel point Etes vous satisfait de votre équilibre viepriéé/vie professionnel? ", "Q6 - A quel point Etes vous satisfait de vos collègues? ", "Q6 - A quel point Etes vous satisfait de votre hiérarchie? ", "Q6 - A quel point Etes vous satisfait de votre avancement? ", "Q6 - A quel point Etes vous satisfait du fait d'apprendre de nouvelles choses? ", "Q7 -A quel point il a été difficile de vous orienter vers la Data?", "Q8 - Si vous recherchiez un nouvel position, quel serait votre priorité?", "Q9 - Masculin/Féminin ?", "Q10 - Age", "Q11 - Dans quel pays habité vous?", "Q12 -Niveau d'éducation ", "Q13 - Ethnie", "Salaire Moyen"}),
	    #"Renamed Columns6" = Table.RenameColumns(#"Removed Other Columns",{{"Q6 - A quel point Etes vous satisfait de votre salaire? ", "Q6A - A quel point Etes vous satisfait de votre salaire?"}, {"Q6 - A quel point Etes vous satisfait de votre équilibre viepriéé/vie professionnel? ", "Q6B - A quel point Etes vous satisfait de votre équilibre viepriéé/vie professionnel?"}, {"Q6 - A quel point Etes vous satisfait de vos collègues? ", "Q6C - A quel point Etes vous satisfait de vos collègues?"}, {"Q6 - A quel point Etes vous satisfait de votre hiérarchie? ", "Q6D - A quel point Etes vous satisfait de votre hiérarchie?"}, {"Q6 - A quel point Etes vous satisfait de votre avancement? ", "Q6E - A quel point Etes vous satisfait de votre avancement?"}, {"Q6 - A quel point Etes vous satisfait du fait d'apprendre de nouvelles choses? ", "Q6F - A quel point Etes vous satisfait du fait d'apprendre de nouvelles choses?"}})
	in
	    #"Renamed Columns6".

Principaux enseignements :
Aussi, il s'agit d'une enquête, il faut présenter les caractéristiques de l'échantillon afin d'en évaluer la représentativité.
[Caractéristiques des enquêtés](/assets/img/Caractéristiques des enquêtés.png)
[Principaux résultats](/assets/img/Principaux résultats.png)

[Projet 2 : Titre du Projet](lien vers le dépôt)

Brève description du projet, outils utilisés, et principaux enseignements.


[Projet 3 : Titre du Projet](lien vers le dépôt)

Brève description du projet, outils utilisés, et principaux enseignements.


## Contact

Je suis toujours ouvert à la connexion avec d'autres professionnels et à discuter d'opportunités de collaboration potentielles. N'hésitez pas à me contacter :

  Email : kikithales@gmail.com
  
  LinkedIn : [thalès-kiki](https://www.linkedin.com/in/thal%C3%A8s-kiki/)
  
  GitHub : [Thales-K](https://github.com/Thales-K)

Merci d'avoir visiter mon portfolio !
