# Panneaux Info Chantier

Application web pour afficher et gérer les informations de chantier avec une interface publique et un panneau administrateur sécurisé.

## 🚀 Installation

### 1. Netlify déploiera automatiquement

Une fois les fichiers sur GitHub, Netlify détecte et déploie automatiquement.

Tu peux voir l'état du déploiement sur [Netlify Dashboard](https://app.netlify.com/)

---

## 🔐 Admin Access

- Bouton **⚙️ Admin** en bas à droite de la page publique
- Mot de passe: `MRS6CDO`

---

## 📊 Initialiser les données dans Supabase

Va dans **SQL Editor** de Supabase et exécute ce SQL :

```sql
-- Ajouter un projet
INSERT INTO projects (title, image_url, surface, usage, amount, address, description)
VALUES (
  'MRS6CDO - Sous-station HTB/HTA 225/20 kV',
  'https://via.placeholder.com/800x300',
  '1986 m²',
  'Infrastructure',
  '20 000 000 € HT',
  '217 rue Eugène Schneider, 13220, Bouc-Bel-Air, France',
  'Le projet consiste en la conception et la construction du poste HTB/HTA 225/20 kV MRSX02.'
);

-- Ajouter les sections
INSERT INTO sections (project_id, name, order_index)
VALUES 
(1, 'Maître d''ouvrage', 1),
(1, 'Contractant général', 2),
(1, 'Maître d''œuvre', 3),
(1, 'Bureau d''étude', 4),
(1, 'Assistant Maître d''ouvrage', 5),
(1, 'Contrôle / Coordinateur SPS', 6);

-- Ajouter infos chantier
INSERT INTO site_info (project_id, start_date, end_date, working_hours, contact_name, contact_email, contact_phone)
VALUES (
  1,
  '29/04/2026',
  '31/03/2028',
  'Lundi: 06:00 - 18:00
Mardi: 06:00 - 18:00
Mercredi: 06:00 - 18:00
Jeudi: 06:00 - 18:00
Vendredi: 06:00 - 18:00',
  'Alexandre GEFFARD',
  'a.geffard@capingelec.com',
  '07 89 54 36 19'
);

-- Ajouter quelques lots
INSERT INTO lots (project_id, name, description, order_index)
VALUES 
(1, 'Lot 00 - Installation de chantier', 'Organisation et logistique du chantier', 1),
(1, 'Lot 01 - VRD', 'Travaux de voiries et réseaux divers', 2);
