---
description: Ajouter une nouvelle entreprise (Tenant) à la plateforme Apizee Embed depuis le Back-Office.
---

# Créer un nouveau Tenant (Entreprise)

{% hint style="info" %}
**Prérequis**

* Vous êtes connecté au Back-Office.
* Vous êtes sur la page de liste des **Tenants**.
{% endhint %}

1. Cliquez sur le bouton **Créer**.
2. Saisissez un **Nom** pour le tenant. Ce champ est obligatoire et doit contenir au moins 3 caractères.
3. Vérifiez le champ **Clé d'identification**. Il est automatiquement rempli avec un slug généré à partir du nom que vous avez saisi. Vous pouvez le modifier si nécessaire.

{% hint style="info" %}
La clé d'identification doit être en minuscules et ne contenir que des lettres, des chiffres et des tirets.
{% endhint %}

4. Cliquez sur **Créer**.

{% hint style="success" %}
Une notification de succès confirme la création du tenant : **\[Nom du tenant\] ajouté. Voir**.

Cliquez sur **Voir** pour ouvrir la page d'informations du nouveau tenant.
{% endhint %}

{% hint style="warning" %}
Si une erreur survient lors de la création, une notification s'affiche :

**Impossible de créer dans \[Back-Office / Cloud / KeyCloak\]. Contactez votre administrateur.**

Ce message reste visible jusqu'à ce que vous le fermiez en cliquant sur le bouton **×**.
{% endhint %}
