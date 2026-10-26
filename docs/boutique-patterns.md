# Pack de Patterns — boutiques et sites de petits commerces

Ce pack ajoute cinq Patterns en français pour passer des informations client à une maquette mobile-first, puis la contrôler. Ils complètent les Patterns généraux de Fabric et peuvent être utilisés séparément.

## Les cinq Patterns

| Pattern | À utiliser pour | Sortie principale |
| --- | --- | --- |
| `brief_boutique_mobile` | Transformer notes et échanges client en cadrage exploitable | Objectif, public, parcours, périmètre et informations à confirmer |
| `normalize_product_catalogue` | Mettre en ordre une liste de produits | JSON structuré, SKU, disponibilité, prix et devise d’origine préservés |
| `spec_mobile_storefront` | Préparer la réalisation d’une boutique | Direction visuelle, sections, composants, responsive et accessibilité |
| `prepare_whatsapp_order_demo` | Définir une demande de commande par messagerie | Parcours, libellés et règles d’un lien WhatsApp conditionnel |
| `audit_mobile_shop_prototype` | Examiner un concept, des captures ou un site rendu | Constats fondés sur des preuves et correctifs prioritaires |

## Parcours conseillé

1. Cadrer le commerce avec `brief_boutique_mobile`.
2. Structurer les produits avec `normalize_product_catalogue` si le site comprend un catalogue.
3. Décrire l’interface avec `spec_mobile_storefront`.
4. Préciser la prise de contact avec `prepare_whatsapp_order_demo` si WhatsApp est un canal confirmé.
5. Contrôler le prototype avec `audit_mobile_shop_prototype`.

Lorsqu’une sortie est réutilisée dans un autre Pattern, conserve les statuts **CONFIRMÉ**, **SUGGESTION** et **À CONFIRMER** sans transformer une proposition en fait établi.

## Installation dans Fabric

Dans Fabric, lance `fabric --setup`, choisis **Custom Patterns** dans le menu Tools et indique un dossier dédié, par exemple `~/fabric-custom-patterns`. Depuis la racine de ce dépôt, copie ensuite les cinq dossiers de Patterns dans ce dossier :

```bash
mkdir -p ~/fabric-custom-patterns
cp -R data/patterns/brief_boutique_mobile \
  data/patterns/normalize_product_catalogue \
  data/patterns/spec_mobile_storefront \
  data/patterns/prepare_whatsapp_order_demo \
  data/patterns/audit_mobile_shop_prototype \
  ~/fabric-custom-patterns/
```

Vérifie qu’ils apparaissent avec `fabric --listpatterns`. Si Fabric ne les trouve pas, relance `fabric --setup` et vérifie que le chemin **Custom Patterns** pointe vers le même dossier.

## Exemples

Après installation ou mise à disposition de ces Patterns dans Fabric, passe les notes par l’entrée standard :

```bash
fabric --pattern brief_boutique_mobile < brief-client.txt
fabric --pattern normalize_product_catalogue < produits.txt
fabric --pattern spec_mobile_storefront < brief-et-catalogue.txt
fabric --pattern prepare_whatsapp_order_demo < parcours-commande.txt
fabric --pattern audit_mobile_shop_prototype < observations-ou-specification.txt
```

Adapte les fichiers d’entrée à ton projet. Un audit de captures ou de texte ne teste pas les interactions d’un site; indique toujours si le navigateur n’a pas été utilisé.

## Garde-fous du pack

- Les valeurs inconnues sont notées « à confirmer »; aucun prix, stock, frais, coordonnée, avis ou argument commercial n’est inventé.
- XOF s’emploie lorsque le contexte burkinabè et la devise sont établis; les autres montants et devises restent préservés tels que fournis, sans conversion automatique.
- Zones, frais et délais de livraison, retours, confidentialité, autorisation d’usage des images et allégations réglementées restent à valider avant publication.
- Un lien WhatsApp actif exige un numéro confirmé et un commerçant qui utilise effectivement ce canal; préparer ou ouvrir un message ne signifie pas qu’il est envoyé.
- Une maquette est identifiée comme démo : une sélection locale n’est pas une commande transmise, et aucun paiement n’est simulé comme réel. Les besoins de production (admin, persistance, stocks, paiements, livraison, sécurité et sauvegardes) doivent être cadrés séparément.
- Les spécifications privilégient téléphone, faible consommation de données, accessibilité et contenu principal visible rapidement.
