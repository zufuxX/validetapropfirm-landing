# ValideTaPropFirm — Landing (version conforme Meta + RGPD)

Refonte conforme de la landing `validetapropfirmad.com`. Même design (carte unique centrée → canal Telegram), mais réécrite pour **passer la review Meta Ads** et respecter le **RGPD / CNIL / LCEN** (audience France).

## Ce qui a changé vs l'originale (et pourquoi)

| Original (rejeté par Meta) | Remplacé par | Règle Meta |
|---|---|---|
| « 100% Réussite Garantie » | « Méthode structurée pour préparer ton challenge » | Misleading Claims / Unrealistic Outcomes (**blocker**) |
| « Paiement après Validation » | Positionnement formation/communauté, sans garantie | Unacceptable Business Practices / get-rich-quick (**blocker**) |
| « 687+ Défis Validés ! » | « Communauté active de traders » | Unsubstantiated performance claim (**high**) |
| « Expert Validation PropFirm » | « Communauté & méthode de préparation » | Unsubstantiated authority + Financial Services |
| Pixel Meta au chargement | Pixel **bloqué jusqu'au consentement** (bannière CNIL) | CNIL/ePrivacy (**blocker**) |
| Aucune mention légale | Mentions légales / Confidentialité / CGU / 18+ / risque | LCEN + RGPD + Code conso |

## Éléments de conformité intégrés
- **Avertissement de risque** visible au-dessus de la ligne de flottaison + version complète repliable (crawlable par Meta).
- **Disclaimer de service / non-affiliation** : VTPF n'est pas une prop firm, ne garantit aucun résultat.
- **Mention 18+** sur la page (pensez aussi à cibler 18+ côté Meta).
- **Bannière cookies CNIL** : « Tout accepter » / « Tout refuser » au même niveau + « Personnaliser » (granularité), choix conservé 6 mois, lien/bouton flottant « Gérer mes cookies », **le pixel Meta ne se déclenche qu'après opt-in**.
- **Footer légal** : Mentions légales · Politique de confidentialité · CGU/CGV · Gérer mes cookies.
- Pages légales : `mentions-legales.html`, `confidentialite.html`, `cgu.html` (modèles avec champs `[entre crochets]` à remplir).

## À renseigner AVANT de lancer des pubs (dans `index.html`)
1. `TELEGRAM_URL` — le lien réel du canal.
2. `META_PIXEL_ID` — votre ID de pixel (laissé vide = pixel jamais chargé, ce qui reste conforme).
3. Tous les champs `[entre crochets]` des pages légales (raison sociale, SIRET, email, médiateur, etc.).
4. (Optionnel) déposer `validetapropfirm.jpeg` dans le dossier et activer la balise `<img>` dans l'avatar.

## Points de vigilance (ne dépendent pas de la page)
- Déclarer la **Special Ad Category « Financial Products and Services »** côté Meta (obligatoire depuis le 21/01/2025) + vérification d'entreprise.
- **Nettoyer le canal Telegram de destination** (Meta crawle la destination finale) : photo, description FR, messages épinglés **sans** promesse de gains / « je passe le challenge à ta place ».
- Vérifier dans les DevTools qu'**aucune requête `facebook.com/tr` ne part avant clic « Tout accepter »**.

> Modèles juridiques fournis à titre indicatif — à faire valider par un conseil avant exploitation commerciale.

## Déploiement
Hébergé sur Vercel, dépôt GitHub `zufuxX/validetapropfirm-landing`, branche `main` (push = déploiement auto en production).
