# 🚀 SDS Enterprise - Salwa Dev Studio

[![CI](https://github.com/Soofmax/SDS-Entreprise/actions/workflows/ci.yml/badge.svg)](https://github.com/Soofmax/SDS-Entreprise/actions/workflows/ci.yml)
[![TypeScript](https://img.shields.io/badge/TypeScript-100%25-blue.svg)](https://www.typescriptlang.org/)
[![Next.js](https://img.shields.io/badge/Next.js-15-black.svg)](https://nextjs.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **Site web professionnel pour Salwa Dev Studio** - Agence de développement web spécialisée dans la création de sites vitrine, e-commerce et applications web pour TPE/PME.

## ✨ Fonctionnalités

### 🎨 **Frontend**
- **Design moderne** avec Tailwind CSS et animations fluides
- **Responsive design** optimisé mobile-first
- **Accessibilité WCAG** complète
- **Performance optimisée** (Lighthouse 95+)
- **SEO avancé** avec métadonnées dynamiques

### ⚙️ **Backend**
- **Next.js 15** avec App Router
- **TypeScript strict** (0% any types)
- **Prisma ORM** avec PostgreSQL
- **NextAuth.js** pour l'authentification
- **API REST** complète et documentée

### 💳 **Paiements**
- **Stripe** pour cartes bancaires
- **Coinbase Commerce** pour cryptomonnaies
- **Facturation automatique**
- **Webhooks sécurisés**

### 📊 **Analytics & Tracking**
- **Google Analytics 4** intégré
- **Tracking événements** avancé
- **Dashboard admin** temps réel
- **Conformité RGPD** avec gestion cookies

### 🛡️ **Sécurité**
- **Rate limiting** intelligent
- **Validation stricte** des données
- **Protection CSRF/XSS**
- **Logs centralisés**

## 🚀 Installation

### Prérequis
- **Node.js** 20+ 
- **npm** 10+
- **PostgreSQL** 14+

### Configuration rapide

```bash
# Cloner le projet
git clone https://github.com/Soofmax/SDS-Entreprise.git
cd SDS-Entreprise

# Installer les dépendances
npm install

# Configurer l'environnement
cp .env.example .env.local
# Éditer .env.local avec vos clés

# Configurer la base de données
npx prisma generate
npx prisma db push
npx prisma db seed

# Lancer en développement
npm run dev
```

Le site sera accessible sur [http://localhost:3000](http://localhost:3000)

## 🔧 Configuration

### Variables d'environnement

```bash
# Base de données
DATABASE_URL="postgresql://user:password@localhost:5432/sds"

# NextAuth
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your-secret-key"

# Stripe
STRIPE_SECRET_KEY="sk_test_..."
STRIPE_WEBHOOK_SECRET="whsec_..."

# Coinbase Commerce
COINBASE_COMMERCE_API_KEY="your-api-key"
COINBASE_COMMERCE_WEBHOOK_SECRET="your-webhook-secret"

# Email (Resend)
RESEND_API_KEY="re_..."

# Google Analytics
NEXT_PUBLIC_GA_ID="G-XXXXXXXXXX"
```

## 📁 Structure du projet

```
├── app/                    # Pages et API routes (App Router)
│   ├── (pages)/           # Pages publiques
│   ├── admin/             # Dashboard administrateur
│   └── api/               # API endpoints
├── components/            # Composants React réutilisables
│   ├── ui/               # Composants de base (shadcn/ui)
│   ├── forms/            # Formulaires
│   └── layout/           # Composants de mise en page
├── lib/                  # Utilitaires et services
│   ├── auth/             # Configuration NextAuth
│   ├── db/               # Client Prisma et utilitaires DB
│   ├── services/         # Services métier
│   └── utils/            # Fonctions utilitaires
├── prisma/               # Schéma et migrations Prisma
├── public/               # Assets statiques
└── types/                # Définitions TypeScript
```

## 🛠️ Scripts disponibles

```bash
# Développement
npm run dev              # Serveur de développement
npm run build           # Build de production
npm run start           # Serveur de production

# Base de données
npm run db:generate     # Générer le client Prisma
npm run db:push         # Synchroniser le schéma
npm run db:migrate      # Créer une migration
npm run db:seed         # Peupler avec des données de test

# Qualité du code
npm run type-check      # Vérification TypeScript
npm run lint            # Linter ESLint
npm run lint:fix        # Corriger automatiquement
npm run format          # Formatter avec Prettier

# Tests
npm run test            # Tests unitaires (Vitest)
npm run test:e2e        # Tests end-to-end (Playwright)
npm run test:coverage   # Couverture de tests
```

## 🎯 Packages proposés

### 📦 **ESSENTIEL** - 3 360€ (au lieu de 4 200€)
- Site vitrine professionnel
- Design responsive sur-mesure
- Optimisation SEO avancée
- Formulaire de contact intelligent
- Maintenance 6 mois incluse

### 📦 **PROFESSIONNEL** - 5 200€ (au lieu de 6 500€) ⭐
- Tout du pack Essentiel
- Système de réservation en ligne
- Espace client personnalisé
- Blog intégré avec CMS
- Analytics et rapports détaillés

### 📦 **BOUTIQUE** - 8 000€ (au lieu de 10 000€)
- Tout du pack Professionnel
- Boutique e-commerce complète
- Gestion automatique des stocks
- Paiements sécurisés (Stripe, PayPal)
- Système de fidélité client

## 🚀 Déploiement

### Vercel (Recommandé)

```bash
# Installer Vercel CLI
npm i -g vercel

# Déployer
vercel --prod
```

### Netlify

```bash
# Build
npm run build

# Déployer le dossier .next
```

### Docker

```bash
# Build de l'image
docker build -t sds-enterprise .

# Lancer le conteneur
docker run -p 3000:3000 sds-enterprise
```

## 📊 Performance

- **Lighthouse Score** : 95+ sur tous les critères
- **Core Web Vitals** : Excellent
- **Accessibilité** : WCAG 2.1 AA compliant
- **SEO** : Optimisé pour les moteurs de recherche

## 🤝 Contribution

1. **Fork** le projet
2. **Créer** une branche feature (`git checkout -b feature/amazing-feature`)
3. **Commit** les changements (`git commit -m 'Add amazing feature'`)
4. **Push** vers la branche (`git push origin feature/amazing-feature`)
5. **Ouvrir** une Pull Request

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

## 👥 Équipe

**Salwa Essaf** - *Fondatrice & Développeuse Full-Stack*
- 🌐 [salwadevstudio.com](https://salwadevstudio.com)
- 📧 contact@salwadevstudio.com
- 💼 [LinkedIn](https://linkedin.com/in/salwa-essaf)

## 🙏 Remerciements

- [Next.js](https://nextjs.org/) pour le framework
- [Tailwind CSS](https://tailwindcss.com/) pour le styling
- [Prisma](https://prisma.io/) pour l'ORM
- [Stripe](https://stripe.com/) pour les paiements
- [Vercel](https://vercel.com/) pour l'hébergement

---

<div align="center">
  <strong>Fait avec ❤️ par Salwa Dev Studio</strong>
</div>
