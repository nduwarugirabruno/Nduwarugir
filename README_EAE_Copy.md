<style>
    .column {
        display: flex;
        flex-direction: column;
        gap: 0.1rem;
    }

    .row {
        display: flex;
        flex-direction: row;
        gap: 1rem;
    }
</style>

<header style="display: flex; justify-content: space-between; align-content: center; align-items: center; background: black; padding: 1rem">
    <img src=".assets/valione-logo.png" alt="@LinkSheikah" height="100" title="Telegram - @LinkSheikah"/>
    <span style="padding: 0; text-align: end; color: white;">
        <h1 style="margin: 0; padding: 0">FICHE TECHNIQUE</h1>
        <h2 style="margin: 0; padding: 0">EAE</h2>
    </span>
</header>

<section class="main-content column" style="width: 100dvw">
    <div class="row" style="margin: 0rem 0">
        <h1 style="display:flex; gap: 1.2rem; align-items: center">
            <span style="background: black; border-radius: 45%; width: 50px; height: 50px; display: flex; align-items: center; justify-content: center; color: white">1</span>
            <span>INFORMATIONS GÉNÉRALES</span>
        </h1>
    </div>
    <div class="column">
        <h2>Nom du projet</h2>
        <p>EAE (Entretien Annuel Échange Etam)</p>
        <h2>Type d’application</h2>
        <p>Application web basée sur Microsoft Power Apps (Canvas App), intégrant des flux Power Automate pour
            l’automatisation des processus, et utilisant SharePoint comme base de données principale. L’application est
            conçue pour une utilisation sur desktop et tablette, avec une interface responsive.</p>
        <h2>Environnements</h2>
        <ul>
            <li><strong>DEV</strong> : Environnement de développement pour les tests unitaires et les itérations
                rapides. URL : <a href="https://make.powerapps.com/environments/b61ff93d-bfc2-e22c-aabb-f7a8d725b0fe/"
                                  target="_blank">[DEV] - EAE</a>. Accès restreint aux développeurs.
            </li>
            <li><strong>TEST</strong> : Environnement de test pour la validation fonctionnelle et les tests
                d’intégration. URL : <a
                        href="https://make.powerapps.com/environments/2e440c47-7955-e096-b08d-592ac7ebfdfa/"
                        target="_blank">[TEST] - EAE</a>. Accès aux testeurs et responsables fonctionnels.
            </li>
            <li><strong>PROD</strong> : Environnement de production pour l’utilisation en live. URL : <a
                    href="https://make.powerapps.com/environments/34880265-b69b-e72b-87ca-878000fc47f8/"
                    target="_blank">[PROD] - EAE</a>. Accès contrôlé via Azure AD (Groupe de sécurité).
            </li>
        </ul>
        <p>Les déploiements entre environnements sont gérés via des solutions Power Apps et prochainement par des
            pipelines CI/CD dans Azure DevOps.</p>
        <h2>Responsables fonctionnels et techniques</h2>
        <ul>
            <li><strong>Responsable fonctionnel</strong> : Bart ZELSMANN (bart.zelsmann@vorstone.com) – Gère les
                exigences métier et la validation des fonctionnalités.
            </li>
            <li><strong>Responsable technique</strong> : Marlane TCHOFO (marlane.tchofo@valione-services.com) –
                Supervise l’architecture, les développements et la maintenance.
            </li>
            <li><strong>Équipe de développement</strong> : Composée de 5 développeurs Power Platform.</li>
        </ul>
        <h2>Objectifs du projet et périmètre fonctionnel</h2>
        <p><strong>Objectifs</strong> : L’application EAE vise à simplifier l’évaluation des compétences et expériences
            des employés au sein de l’entreprise, en automatisant les processus de soumission, revue et approbation des
            évaluations. Elle permet une gestion centralisée des données RH pour améliorer la productivité et la
            conformité.</p>
        <p><strong>Périmètre fonctionnel</strong> :</p>
        <ul>
            <li>Gestion des profils utilisateurs (collaborateurs, managers, RH).</li>
            <li>Soumission et revue d’évaluations annuelles ou ponctuelles.</li>
            <li>Tableaux de bord pour le suivi des statuts et rapports analytiques.</li>
            <li>Intégration avec des outils externes comme Outlook/Microsoft Teams pour les notifications.</li>
            <li>Génération de rapports PDF et export vers Excel.</li>
        </ul>
        <!--<p>Hors périmètre : Intégration avec systèmes legacy HR non basés sur Microsoft 365, ou fonctionnalités avancées d’IA pour l’analyse prédictive.</p>        <h2>Sources de données et connecteurs utilisés</h2>-->
        <ul style="display: flex; flex-direction: column; gap: 1rem; margin-top: 0">
            <li><strong>Sources principales</strong> : SharePoint (tables personnalisées pour les environnements de DEV,
                TEST et PROD):
                <ul>
                    <li>Sources partagées aux différents environnements:
                        <ul>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/Liste_Collaborateur_Et_responsable_EAE_Entra_AD/AllItems.aspx" id="Liste_Collaborateur_Et_responsable_EAE_Entra_AD">Liste_Collaborateur_Et_responsable_EAE_Entra_AD</a> : Liste des collaborateurs/managers de SMAC.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/regionAgenceEtablissement/AllItems.aspx">regionAgenceEtablissement</a> : Liste des régions, agences et établissements.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/listeFormation/AllItems.aspx">listeFormation</a> : Liste des formation disponibles.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/template/Forms/AllItems.aspx">template</a> : Bibliothèque contenant le template du document récapitulatif de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/list_de_fiche_poste/AllItems.aspx">list_de_fiche_poste</a> : Liste des fiches de poste disponibles.</li>
                        </ul>
                    </li>
                    <li>Environnement de DEV:
                        <ul>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/Entretien_dechanges_ETAM_et_CADRES/AllItems.aspx">DEV_EAE_P1</a> : Liste de sauvegarde des données de la partie 1 du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/Entretien_dechanges_ETAM_et_CADRES_PARTIE_2/AllItems.aspx">DEV_EAE_P2</a> : Liste de sauvegarde des données de la partie 2 du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/Entretien_dechanges_ETAM_et_CADRES_PARTIE_3/AllItems.aspx">DEV_EAE_P3</a> : Liste de sauvegarde des données de la partie 3 du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/DEV_FORMATION_EAE/AllItems.aspx">DEV_FORMATION_EAE</a> : Liste de sauvegarde des données de formation du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/stockageDoc/Forms/AllItems.aspx">DEV_EAE_STOCKAGE_DOC</a> : Bibliothèque de sauvegarde des documents récapitulatifs de l'EAE.</li>
                        </ul>
                    </li>
                    <li>Environnement de TEST:
                        <ul>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/TEST_EAE_P1/AllItems.aspx">TEST_EAE_P1</a> : Liste de sauvegarde des données de la partie 1 du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/TEST_EAE_P2/AllItems.aspx">TEST_EAE_P2</a> : Liste de sauvegarde des données de la partie 2 du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/TEST_EAE_P3/AllItems.aspx">TEST_EAE_P3</a> : Liste de sauvegarde des données de la partie 3 du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/TEST_FORMATION_EAE/AllItems.aspx">TEST_FORMATION_EAE</a> : Liste de sauvegarde des données de formation du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/TEST_EAE_STOCKAGE_DOC/Forms/AllItems.aspx">TEST_EAE_STOCKAGE_DOC</a> : Bibliothèque de sauvegarde des documents récapitulatifs de l'EAE.</li>
                        </ul>
                    </li>
                    <li>Environnement de PROD:
                        <ul>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/PROD_EAE_P1/AllItems.aspx">PROD_EAE_P1</a> : Liste de sauvegarde des données de la partie 1 du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/PROD_EAE_P2/AllItems.aspx">PROD_EAE_P2</a> : Liste de sauvegarde des données de la partie 2 du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/PROD_EAE_P3/AllItems.aspx">PROD_EAE_P3</a> : Liste de sauvegarde des données de la partie 3 du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/Lists/PROD_FORMATION_EAE/AllItems.aspx">PROD_FORMATION_EAE</a> : Liste de sauvegarde des données de formation du formulaire de l'EAE.</li>
                            <li><a href="https://groupesmac.sharepoint.com/sites/services-rh/PROD_EAE_STOCKAGE_DOC/Forms/AllItems.aspx">PROD_EAE_STOCKAGE_DOC</a> : Bibliothèque de sauvegarde des documents récapitulatifs de l'EAE.</li>
                        </ul>
                    </li>
                </ul>
            </li>
            <li><strong>Connecteurs</strong> :
                <ul>
                    <li><strong>Microsoft Graph API</strong> pour la récupération des données des collaborateurs/managers depuis Entra AD.</li>
                    <li><strong>Microsoft Teams</strong> pour la planification des meetings.</li>
                    <li><strong>Office 365 Users</strong> pour la gestion des profils Azure AD.</li>
                    <li><strong>Office 365 Outlook</strong> pour les notifications.</li>
                    <li><strong>OneDrive Enterprise</strong> pour les backups.</li>
                    <li><strong>Plumsail Documents</strong> pour la conversion des documents lors de l'export.</li>
                    <li><strong>SharePoint</strong> pour le stockage des données.</li>
                    <li><strong>Word Online (Business)</strong> pour la templatisation et génération des documents.</li>
                </ul>
            </li>
            <li><strong>Flows Power Automate</strong> :
                <ul>
                    <li><strong>[PROD] – Lancement Campagne EAE</strong> : Lancement de campagne des entretiens annuels.</li>
                    <li><strong>[PROD] – Relance Campagne EAE</strong> : Relance des entretiens pas commencés.</li>
                    <li><strong>[PROD] – Generation PDF EAE</strong> : Génère le document récapitulatif de l’entretien d’un collaborateur.</li>
                    <li><strong>[PROD] – Lancement Meeting EAE</strong> : Programme un entretien physique pour un collaborateur et le notifie.</li>
                    <li><strong>[PROD] – Gestion des droits EAE</strong> : Attribut les droits de sécurité aux éléments enregistrés dans la liste SharePoint.</li>
                    <li><strong>[PROD] – Save Campagne EAE</strong> : Enregistre les données d’un entretien.</li>
                    <li><strong>[PROD] – Get Collaborators And Managers Lancement Campagne EAE</strong> : Récupère les données des collaborateurs correspondants aux filtres de lancement de campagne.</li>
                    <li><strong>[PROD] – Backup Campaigns EAE</strong> : Sauvegarde les données des campagnes sur OneDrive.</li>
                    <li><strong>[PROD] – Unlock or Lock Interview EAE</strong> : Déverrouille/Verrouille un entretien.</li>
                    <li><strong>[PROD] – Vidage de Listes EAE</strong> : Vide les listes SharePoint contenant les données des entretiens.</li>
                    <li><strong>[PROD] – Suppression Donnees Collaborateur EAE</strong> : Supprime les données d’un collaborateur (RGPD).</li>
                </ul>
            </li>
        </ul>
        <h2>Sécurité globale et règles d’accès</h2>
        <p><strong>Sécurité globale</strong> : L’application utilise Azure Active Directory (AAD) pour
            l’authentification. Les données sont chiffrées au repos et en transit via SharePoint. Conformité RGPD avec
            gestion des consents et audits.</p>
        <p><strong>Règles d’accès</strong> :</p>
        <ul>
            <li>Rôles :
                <ul>
                    <li>Collaborateur (édition sur ses évaluations),</li>
                    <li>Manager N+1 (édition sur évaluations collaborateurs),</li>
                    <li>Manager N+2 (lecture seule sur les évaluations des subordonnées de ses collaborateurs),</li>
                    <li>RH (accès total).</li>
                </ul>
            </li>
            <li>Sécurité : Basée sur les rôles via des groupes SharePoint.</li>
            <li>Accès conditionnel : Basée sur les rôles via des groupes SharePoint.</li>
            <!--<li>Audits : Logs des accès et modifications stockés dans SharePoint pour traçabilité.</li>-->
        </ul>
    </div>
    <div class="row" style="margin: 0rem 0">
        <h1 style="display:flex; gap: 1.2rem; align-items: center;">
            <span style="background: black; border-radius: 45%; width: 50px; height: 50px; display: flex; align-items: center; justify-content: center; color: white">2</span>
            <span>LOGIQUES TECHNIQUES PRINCIPALES</span>
        </h1>
    </div>
    <div class="column">
        <h2>Logique d’affichage des écrans selon le rôle utilisateur</h2>
        <div style="display:flex; flex-direction: column">
            <span>L’affichage/accès des écrans est géré via des variables globales initialisées lors de la connexion (OnStart/StartScreen de
            l’app).</span>
            <span>Les rôles sont déterminés par deux colones de la liste <a href="#Liste_Collaborateur_Et_responsable_EAE_Entra_AD">Liste des collaborateurs et responsables</a> :</span>
            <ul style="margin-top: 0.5rem">
                <li><strong>status (Manager / Collaborateur)</strong> : Représentant le type d'utilisateur.</li>
                <li><strong>user_kind (DRH / RRH / FORMATION)</strong> : Représentant les groupes SharePoint.</li>
            </ul>
        </div>
        <h2>Logique d’affichage et filtrage des données</h2>
        <table style="border-collapse: collapse; width: auto; margin: 1rem 0;">
            <thead>
                <tr style="background-color: #f0f0f0;">
                    <th style="padding: 0.5rem; text-align: left;">Écran</th>
                    <th style="padding: 0.5rem; text-align: center;">Collaborateur</th>
                    <th style="padding: 0.5rem; text-align: center;">Manager</th>
                    <th style="padding: 0.5rem; text-align: center;">RH (DRH)</th>
                    <th style="padding: 0.5rem; text-align: center;">Groupe Formation</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td style="padding: 0.5rem;"><strong>HomeScreen</strong></td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                </tr>
                <tr style="background-color: #f9f9f9;">
                    <td style="padding: 0.5rem;"><strong>HomeRHScreen</strong></td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                </tr>
                <tr>
                    <td style="padding: 0.5rem;"><strong>HomeFormation</strong></td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                </tr>
                <tr style="background-color: #f9f9f9;">
                    <td style="padding: 0.5rem;"><strong>FormScreen</strong></td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                </tr>
                <tr>
                    <td style="padding: 0.5rem;"><strong>StartCampaignScreen</strong></td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                </tr>
                <tr style="background-color: #f9f9f9;">
                    <td style="padding: 0.5rem;"><strong>DashboardScreen</strong></td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                    <td style="padding: 0.5rem; text-align: center;">✓</td>
                    <td style="padding: 0.5rem; text-align: center;">✗</td>
                </tr>
            </tbody>
        </table>
        <p>Les galeries et tableaux utilisent des collections chargées via les formules <code>Collect(...)</code>, <code>ClearCollect(...)</code>, <code>Filter(...)</code>, <code>Distinct(...)</code> et <code>Search(...)</code> pour filtrer les données.</p>
        <ul>
            <li><strong>Filtrage dynamique</strong> : Basé sur des dropdowns (e.g statut, codeFonction, année, titre de la campagne).</li>
            <li><strong>Pagination</strong> : Implémentée avec des <code>ClearCollect(...)</code> pour charger les données par lots d'enregistrements.</li>
            <li><strong>Affichage conditionnel</strong> : Contrôles visibles (e.g <code>Visible = IS_RH</code>, <code>Visible = IS_FORMATION</code>).</li>
        </ul>
        <h2>Règles métier critiques et transitions de statuts</h2>
        <p><strong>Règles critiques</strong> : Une évaluation ne peut être soumise que si tous les champs obligatoires sont remplis (validation via la propriété
                <code>DisplaMode</code> d'une checkbox).</p>
        <p><strong>Transitions de statuts</strong> : Gérées via les champs <strong><i>Statut Collaborateur</i></strong> et <strong><i>Statut Manager</i></strong> dans SharePoint (Pas commencé → En cours → Partagé → À signer → Terminé).</p>
        <ul>
            <li>De "Pas commencé" à "En cours" : Automatique via Power Automate sur mise à jour.</li>
            <li>Seul un Manager peut passer son statut à "Terminé" et celui de son collaborateur à "À signer".</li>
            <li>Seul un Collaborateur peut passer son statut à "Terminé".</li>
        </ul>
        <h2>Logique de visibilité et d’édition des contrôles</h2>
        <p>Mode d'affichage du formulaire : <code>Mode = If("Statut Collaborateur'.Value = "Terminé" Or varSuperRespo, FormMode.View, FormMode.Edit)</code>.</p>
        <h2>Flows Power Automate : déclencheurs et conditions principales</h2>
        <ul>
            <li><strong>[PROD] – Lancement Campagne EAE</strong> :
                <ul>
                    <li>Déclencheur instantané (<i>When Power Apps calls a flow (V2)</i>).</li>
                    <li>Condition : Si collaborateur a un manager, crée un entretien.</li>
                    <li>Envoi un email sur l'entretien nouvellement crée au manager et collaborateur via Outlook (<i>Send an email (V2)</i>).</li>
                </ul>
            </li>
            <li><strong>[PROD] – Relance Campagne EAE</strong> :
                <ul>
                    <li>Déclencheur instantané (<i>When Power Apps calls a flow (V2)</i>).</li>
                    <li>Condition : Si le Statut Manager est à "Pas commencé", envoi un email sur l'entretien au manager via Outlook (<i>Send an email (V2)</i>).</li>
                </ul>
            </li>
            <li><strong>[PROD] – Generation PDF EAE</strong> :
                <ul>
                    <li>Déclencheur instantané (<i>When Power Apps calls a flow (V2)</i>).</li>
                    <li>Condition : Si le Statut Collaborateur est à "Pas commencé", génère le document récapitulatif de l'entretien via le <i>Populate Word Template</i>.</li>
                    <li>Envoi un email contenant le document récapitulatif de l'entretien au manager et au collaborateur via Outlook (<i>Send an email (V2)</i>).</li>
                </ul>
            </li>
            <li><strong>[PROD] – Lancement Meeting EAE</strong> :
                <ul>
                    <li>Déclencheur instantané (<i>When Power Apps calls a flow (V2)</i>).</li>
                    <li>Condition : Si le Statut Collaborateur est à "Pas commencé", génère le document récapitulatif de l'entretien via le <i>Populate Word Template</i>.</li>
                    <li>Envoi un email contenant le document récapitulatif de l'entretien au manager et au collaborateur via Outlook (<i>Send an email (V2)</i>).</li>
                </ul>
            </li>
            <li><strong>[PROD] – Gestion des droits EAE</strong> :
                <ul>
                    <li>Déclencheur automatique (<i>When an item is created</i>) de SharePoint.</li>
                    <li>Envoi des requêtes SharePoint (<i>Send an HTTP request to SharePoint</i>) pour redéfinir les permissions/accèss aux items crées dans les différentes listes SharePoint par environnement.</li>
                </ul>
            </li>
            <li><strong>[PROD] – Save Campagne EAE</strong> :
                <ul>
                    <li>Déclencheur instantané (<i>When Power Apps calls a flow (V2)</i>).</li>
                    <li>Condition : Si l'ID de l'item passé comme paramètre est null, mets à jour les données dans les listes SharePoint correspondantes via <i>Update Item</i> de SharePoint.</li>
                </ul>
            </li>
            <li><strong>[PROD] – Get Collaborators And Managers Lancement Campagne EAE</strong> :
                <ul>
                    <li>Déclencheur instantané (<i>When Power Apps calls a flow (V2)</i>).</li>
                    <li>Retourne la liste de collaborateur/manager correspondants aux filtres.</li>
                </ul>
            </li>
            <li><strong>[PROD] – Backup Campaigns EAE</strong> :
                <ul>
                    <li>Déclencheur instantané (<i>When Power Apps calls a flow (V2)</i>).</li>
                    <li>Crée les dossiers JSONs, CSVs et PDFs contenants respectivement les fichiers json, csv des parties 1, 2 et 3 du formulaire d'évaluation ainsi que les fichiers pdf des documents récapitulatifs des entretiens via <i>Create File</i> de OneDrive.</li>
                </ul>
            </li>
            <li><strong>[PROD] – Unlock or Lock Interview EAE</strong> :
                <ul>
                    <li>Déclencheur instantané (<i>When Power Apps calls a flow (V2)</i>).</li>
                    <li>Condition : Si le MODE est égal à "UNLOCK" :
                        <ul>
                            <li>Condition : Si le "Statut Collaborateur" est passé à "Terminé" :</li>
                            <li>Passe le "Statut Manager" à "En cours",</li>
                            <li>Supprime le document récapitulatif de l'entretien généré.</li>
                        </ul>
                    </li>
                    <li>Notifie le collaborateur et le manager via email le déblocage de l'entretien via Outlook (<i>Send an email (V2)</i>).</li>
                </ul>
            </li>
            <li><strong>[PROD] – Vidage de Listes EAE</strong> :
                <ul>
                    <li>Déclencheur instantané (<i>Manually trigger a flow</i>).</li>
                    <li>Vide les différentes listes (Partie 1, 2 et 3 ainsi que formation) via <i>For each</i>, <i>Get Items</i> et <i>Delete Item</i> de SharePoint.</li>
                </ul>
            </li>
            <li><strong>[PROD] – Suppression Donnees Collaborateur EAE</strong> :
                <ul>
                    <li>Déclencheur instantané (<i>When Power Apps calls a flow (V2)</i>).</li>
                    <li>Supprime les données des collaborateurs des différentes listes (Partie 1, 2 et 3 ainsi que formation) via <i>For each</i>, <i>Get Items</i> et <i>Delete Item</i> de SharePoint.</li>
                </ul>
            </li>
        </ul>
        <h2>Points de vigilance et limitations connues</h2>
        <ul>
            <li><strong>Vigilance</strong> : Performances sur les collections > 2000 items ; utiliser délégation avec
                Filter/Search.
            </li>
            <li><strong>Limitations</strong> : Power Apps limite à 2000 enregistrements par requête sans délégation. Pas
                de support natif pour les jointures complexes ; utiliser des vues SharePoint.
            </li>
            <li>Surveiller les quotas Power Automate (runs par jour).</li>
        </ul>
        <h2>Exemples de formules Power Fx ou expressions clés</h2>
        <ul>
            <li>Chargement collection : <code>ClearCollect(colEvaluations, Filter(Evaluations, Owner.Email =
                varUser.Email))</code></li>
            <li>Validation : <code>If(IsBlank(TextInput.Text), Notify("Champ obligatoire",
                NotificationType.Error))</code></li>
            <li>Soumission : <code>Patch(Evaluations, Defaults(Evaluations), {Statut: "Soumis"})</code></li>
            <li>Filtre avancé : <code>SortByColumns(Filter(colEvaluations, StartsWith(Titre, SearchInput.Text)), "Date",
                Descending)</code></li>
        </ul>
    </div>
</section>

<footer>
    <p>Document mis à jour le : 18/01/2026 | Version : 1.0 | Auteur : <strong>Bruno NDUWARUGIRA</strong>.</p>
</footer>