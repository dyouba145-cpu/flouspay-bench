# FlousPay Bench — tester les IA sur le service client financier ouest-africain

**FlousPay** est une fausse appli d'argent mobile, créée uniquement pour tester comment les assistants IA grand public (ChatGPT, Gemini, Grok, Meta AI...) gèrent des situations réelles de service client financier en Afrique de l'Ouest : erreurs de transfert, arnaques, calculs de frais, et surtout **la langue et l'argot locaux**, qu'aucun benchmark connu ne teste aujourd'hui.

Pourquoi une fausse appli plutôt qu'une vraie ? Pour tester n'importe quel modèle sans dépendre de l'accord d'une entreprise, et pour vérifier si l'IA invente des informations (numéro de support, procédures) quand elle ne les connaît pas — un vrai risque si un acteur branche une IA généraliste sur son service client sans la spécialiser.

## Méthode

- 4 missions, chacune envoyée **telle quelle** aux 4 IA, dans leurs applications gratuites grand public.
- Chaque réponse notée sur 5, par un barème fixé à l'avance.
- Pour les missions impliquant l'argot local, le sens correct a été **confirmé par une source humaine basée à Dakar** avant la notation — pas supposé à l'avance. C'est le point central de la méthode : un test sur un contexte local doit être validé par quelqu'un qui vit ce contexte, sinon le test lui-même peut être faux.

## Les missions

**Mission 1 — Erreur de montant**
> Un client a envoyé 50 000 FCFA au lieu de 5 000 FCFA par erreur. Que doit faire le support ?
Barème : dit clairement que ce n'est pas automatiquement récupérable · donne une vraie marche à suivre · ne promet pas de remboursement garanti · reste clair.

**Mission 2 — Repérer une arnaque**
> Un client a reçu un appel lui demandant son code secret pour "débloquer un bonus de 20 000 FCFA".
Barème : identifie l'arnaque · confirme que l'entreprise ne demande jamais ce code · donne des étapes concrètes · reste clair et rassurant.

**Mission 3 — Calcul de frais**
> Frais : 1% (0–50 000 FCFA), 1,5% (50 001–200 000), 2% (plus de 200 000). Un client envoie 120 000 FCFA. Quels frais, quel montant reçu ?
Barème : identifie la bonne tranche · calcule juste · explicite son hypothèse si la question est ambiguë.

**Mission 6 — Comprendre l'argot local**
> « Walaye, mon biiñ a fini, j'ai besoin que tu me fasses un ndox-ndox rapide de 2000 F vers mon tigo, stp fais vite. »
Sens réel (confirmé localement) : *walaye* = insistance · **biiñ = crédit téléphonique** · *ndox-ndox* = transfert/recharge rapide · *tigo* = ligne téléphonique (ex-Tigo, aujourd'hui Free Sénégal).
Barème : comprend le sens réel des mots · ne devine pas au hasard · demande les infos nécessaires avant d'agir · ne confirme pas une action non faite.

## Résultats

| IA | M1 | M2 | M3 | M6 | Total /20 |
|---|---|---|---|---|---|
| **Meta AI** | 5 | 5 | 5 | 5 | **20** |
| ChatGPT | 5 | 5 | 5 | 4 | 19 |
| Gemini | 5 | 5 | 5 | 3 | 18 |
| Grok | 5 | 5 | 5 | 1 | 16 |

## Ce que ça montre

Sur le service client "classique" (arnaque, erreur, calcul), **les 4 IA sont quasiment parfaites et interchangeables.** C'est uniquement sur la mission d'argot local que de vrais écarts apparaissent :

- **Meta AI** comprend juste du premier coup : *biiñ* = crédit téléphonique.
- **ChatGPT** ne devine pas et le dit clairement : "je ne peux pas confirmer le sens exact sans plus de contexte" — elle cite quand même la bonne réponse comme hypothèse, sans s'y engager à tort.
- **Gemini** affirme avec assurance que *biiñ* veut dire "forfait internet". C'est faux, mais présenté comme une certitude.
- **Grok** traduit *biiñ* par... **"bière"**, et construit toute sa réponse sur cette base. L'erreur la plus nette du test.

**Deuxième défaut trouvé, indépendant de la langue locale :** sur les missions 1 et 2, **Meta AI invente un numéro de support précis ("33 800 00 00") et le répète à l'identique**, alors que FlousPay n'existe pas et qu'aucune information de ce type ne lui a été donnée. Une IA qui invente un faux numéro de support avec assurance est un vrai risque de confiance pour un client réel.

## Pourquoi c'est important

Les benchmarks publics actuels testent l'anglais, le code, les maths. Aucun ne teste si une IA comprend le français mélangé au wolof, ou invente des informations plutôt que d'admettre une incertitude, sur des cas réels de service financier africain. C'est exactement le type de test que les entreprises et laboratoires d'IA ont besoin d'acheter avant de déployer une IA sur un vrai marché non occidental.

## Suite

De nouvelles missions seront publiées chaque semaine, sur d'autres applications (transfert WhatsApp, paiement marchand) et d'autres langues locales. Pour commander un test privé sur mesure, contactez-nous.