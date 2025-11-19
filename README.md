# 🔐 Svelte Password Input  
Un champ **mot de passe intelligent** pour Svelte 5 – avec vérification en temps réel, animations fluides et accessibilité.

[![NPM](https://img.shields.io/npm/v/@salvadorgriaule/svelte-password-input?color=red)](https://npmjs.com/package/@salvadorgriaule/svelte-password-input)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
![Svelte 5](https://img.shields.io/badge/Svelte-5-orange)

---

## ✨ Fonctionnalités
- ✅ Validation **live** (longueur, majuscule, minuscule, chiffre, caractère spécial)  
- ✅ Animation **anime.js** de la zone de critères  
- ✅ Mode « création » ou « changement » de mot de passe  
- ✅ Icônes SVG accessibles  
- ✅ Zero dépendance **runtime** (hors dev)  
- ✅ Full TypeScript  

---

## 📦 Installation

```bash
npm i @salvadorgriaule/svelte-password-input
# ou
pnpm add @salvadorgriaule/svelte-password-input
```

---

## 🚀 Utilisation rapide

```svelte
<script lang="ts">
  import PasswordInput from "@salvadorgriaule/svelte-password-input";

  let ok = $state(false);
  let pwd  = $state("");
</script>

<PasswordInput bind:boolPW={ok} bind:Password={pwd} />
<button disabled={!ok}>S'inscrire</button>
```

---

## 📌 Props

| Prop          | Type      | Défaut | Description |
|---------------|-----------|--------|-------------|
| `changeMode`  | `boolean` | `false` | Placeholder « Nouveau mot de passe » |
| `boolPW`      | `boolean` | `false` | `true` si tous les critères sont remplis (bindable) |
| `greatPW`     | `string`  | `""`    | Classe CSS appliquée au champ (bindable) |
| `Password`    | `string`  | `""`    | Valeur du mot de passe (bindable) |

---

## 🎨 Classes CSS générées

Le champ bascule automatiquement entre :
- `border-red-500` – au moins 1 critère manquant  
- `border-green-600` – tous les critères remplis  

Vous pouvez surcharger ces classes dans votre feuille de style.

---

## 🧪 Critères vérifiés

| Règle | Expression |
|-------|------------|
| ≥ 8 caractères | `.{8,}` |
| 1 chiffre | `\d` |
| 1 majuscule | `[A-Z]` |
| 1 minuscule | `[a-z]` |
| 1 spécial | `[#~!?,.§€$£%:*()]` |

---

## 🛠️ Développement

```bash
git clone https://github.com/SalvadorGriaule/PasswordInput.git
cd PasswordInput
pnpm i
pnpm dev
```

Ouvrez `http://localhost:5173` – le dossier `src/lib` contient le composant.

---

## 📁 Structure

```
src/
├── lib/
│   ├── PasswordInput.svelte   # composant principal
│   ├── CheckSvg.svelte        # icône animée
│   └── inputCheck.ts          # logique de validation
└── routes/+page.svelte        # démo
```

---

## 🧩 Accessibilité

- Label implicite via `placeholder`  
- Icônes accompagnées de textes visibles  
- Pas de dépendance à la souris (navigation clavier complète)

---

## 📝 Licence

MIT – feel free to use, fork, remix.

---

## 🤝 Contributions

Les PR sont les bienvenues !  
1. Forkez  
2. Créez une branche `feat/xxx`  
3. `pnpm check && pnpm test` ✅  
4. Ouvrez une Pull Request

---

Une ⭐ star fait toujours plaisir !