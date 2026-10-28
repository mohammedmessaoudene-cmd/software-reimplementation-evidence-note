# Évaluer une réimplémentation logicielle : preuves et limites d’une note partielle

**Messaoudene NT Interop — note méthodologique partielle, version `v0.1.0-methods-note`, 28 octobre 2026.** Direction et attribution : Professeur Messaoudene ; prose préparée avec assistance IA. Licence CC BY 4.0 limitée à la prose originale de cette sélection, avec exclusions dans [RIGHTS_AND_RELEASE_DECISIONS](RIGHTS_AND_RELEASE_DECISIONS.md).

## Objet de la note

Une réimplémentation peut produire la réponse attendue tout en réalisant un mécanisme différent de celui qui était exigé. Pour évaluer une opération de synchronisation, une ligne `PASS` ou un code de sortie favorable ne suffit donc pas. Il faut définir le comportement demandé, identifier la version testée et relier l’observation à une invocation précise. Un contrôle négatif pertinent doit ensuite montrer que le banc refuse le défaut qu’il prétend détecter. Cette note développe cette méthode et un exemple historique étroit. [P01–P02]

Le projet étudie un sous-ensemble expérimental d’événements de synchronisation et d’état d’erreur par thread. Cette sélection ne permet pas d’évaluer un système d’exploitation complet. La présente édition rassemble une explication originale et des références de preuve ; aucun code, binaire ou journal privé n’est joint. Les lecteurs peuvent examiner le raisonnement et les références publiques. Ils ne peuvent pas reproduire l’expérience historique à partir de cette seule édition. [P03, P06]

## Une chaîne de preuve vérifiable

Le contrat expérimental doit préciser les opérations admises, les erreurs retenues, les limites de concurrence et ce qui constitue une réussite. Dans une comparaison binaire, la sonde utilisée des deux côtés doit avoir l’identité annoncée. Une empreinte permet de comparer des octets ; elle ne prouve ni leur origine, ni l’exécution, ni la correction du résultat. [P01]

| Élément | Question à résoudre |
|---|---|
| Contrat | Quelle propriété est réellement demandée ? |
| Identité | Quelle sonde, quelle cible et quelle configuration ont été utilisées ? |
| Mécanisme causal | L’attente concernée a-t-elle provoqué le blocage et la reprise annoncés ? |
| Négatif discriminant | Le banc refuse-t-il une variante qui supprime précisément cette propriété ? |
| Assesseur | Ses règles vérifient-elles la preuve pertinente plutôt que le seul texte affiché ? |

Pour une attente bloquante, le récit causal attendu relie l’entrée de l’API, l’état du thread, son retrait des contextes exécutables, la cause du réveil, la sélection de son contexte et le retour de la même invocation. Ces observations ont des forces différentes : une ligne interne déclarant un blocage n’est pas une inspection indépendante du processeur. Les versions du producteur et du validateur doivent rester attachées aux traces. [P01, P03]

## Exemple historique : un timeout immédiat pourtant affiché PASS

Un enregistrement interne conservé de la lignée I5 rapporte une variante qui rendait immédiatement le résultat d’expiration d’une attente finie. Dans ce scénario, la sonde imprimait `T07_timeout_result PASS`, annonçait une durée interne nulle et terminait avec le code 0. Le reçu QEMU indiquait 97, code de la voie de sortie attendue de ce projet, sans portée universelle pour QEMU. Le validateur refusait cependant le cas avec notamment `FINITE_TIMEOUT_WITHOUT_BLOCK`. [P02]

La chaîne enregistrée reliait l’entrée de l’attente et son retour à la même invocation, sans blocage intermédiaire. Selon cet enregistrement, le validateur a refusé ce défaut malgré la sortie positive. Il ne démontre pas une durée physique indépendante : une horloge interne et des instants d’arrivée de messages restent des mesures différentes. Il ne garantit pas non plus que l’assesseur détecte tous les faux timeouts. [P02, P04]

Les empreintes des pièces de référence sont indiquées dans [CLAIMS_AND_EVIDENCE](CLAIMS_AND_EVIDENCE.md). Les pièces brutes restent privées. L’exemple est attribué à un dossier historique local ; aucune reproduction indépendante ni nouvelle exécution n’est revendiquée par cette note. Une empreinte sans fichier accessible est un engagement d’identité utile pour une future comparaison, pas un jeu de données publiquement rejouable. [P02–P03]

## Séparer les catégories et les versions

Le dossier interne comprend des observations historiques de sondes sur Windows, des observations invitées QEMU de la lignée I5, des tests de composants C sous Linux et des modèles ou API factices. Ces catégories répondent à des questions différentes. Un test Linux de structure de cadre ne démontre pas une commutation matérielle ; un modèle de handles ne démontre pas leur identité Windows ; un journal QEMU ne constitue pas à lui seul une observation exhaustive des instructions. [P03]

La révision ultérieure T09 possède un oracle Windows historique reçu et une image EFI normale construite. Son exécution invitée n’est pas acquise ; son mutant à état d’erreur global reste non construit et non exécuté. Les résultats I5 ne sont pas transférés à ce successeur. Le lot technique I19 est clos sous `HOLD/STOP_AT_HOLD` ; I20 est un travail de sélection textuelle. [P04]

## Ce qui reste ouvert

Le protocole expérimental local du projet, R7, conserve plusieurs exigences non remplies : deux waiters invités déjà bloqués avant signal, une durée d’API indépendante et calibrée, l’intercalation invitée discriminante de l’état d’erreur par thread, des cas réservés après gel et l’achèvement de l’ensemble prévu et borné de contrôles négatifs. J3/J4 sont historiques et partiels ; J5 n’est pas acquis et `BOUNDED_PASS=false`. [P04]

Une note partielle de méthode reste distincte d’une démonstration R7 complète. Toute preuve future doit être liée à sa version, son environnement, son oracle et ses conditions de réfutation. [P01, P04]

## Proposition d’étude comparative et portée publique

L’effet de l’assistance IA sur l’effort de réimplémentation demeure une question à mesurer ici. Une étude utile comparerait des tâches et critères d’acceptation identiques, avec et sans assistance déclarée, en comptant temps humain, calcul, validation, corrections et maintenance. Il faudrait traiter séparément coût initial, qualité et capacité à maintenir le résultat. Les observations retenues ne permettent pas d’attribuer un gain causal à l’IA ou un dommage économique au secteur. [P05]

Une discussion de politique publique peut aussi examiner les bénéfices possibles de l’interopérabilité, de la recherche et de la concurrence, ainsi que les coûts de provenance et de maintenance. Des exigences proportionnées d’attribution, de transparence sur les méthodes et d’explicitation des preuves sont des options à discuter. Elles ne sont pas des règles nouvelles adoptées par une institution. La similarité fonctionnelle seule ne décide pas la copie d’une expression protégée ou l’illégalité d’une réimplémentation. [P05–P06 ; S01, S07]

La prose originale sélectionnée est diffusée sous CC BY 4.0 dans la limite des droits détenus par Professeur Messaoudene. Cette licence ne couvre ni les archives probatoires privées, ni le code expérimental, ni les œuvres tierces liées. Les licences d’outils utilisés mais non joints ne deviennent pas la licence de la note. Cette publication partielle ne satisfait pas J5 et ne prétend pas satisfaire R7. [P06 ; S02–S05, S08]
