# 🚀 Guide de Mise en Production - SDS

## 📋 Checklist Avant Production

### ✅ 1. Configuration des Variables d'Environnement

Modifiez le fichier `.env.local` :

#### 🏠 Application
```env
NEXT_PUBLIC_APP_URL=https://votre-domaine.com
NODE_ENV=production
```

#### 💳 Stripe (Paiements)
1. Créez un compte sur [stripe.com](https://stripe.com)
2. Récupérez vos clés dans Dashboard > Developers > API keys
3. Remplacez dans `.env.local` :
```env
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=pk_live_votre_cle_publique
STRIPE_SECRET_KEY=sk_live_votre_cle_secrete
STRIPE_WEBHOOK_SECRET=whsec_votre_webhook_secret
```

#### 📧 Emails (Resend)
1. Créez un compte sur [resend.com](https://resend.com)
2. Ajoutez votre domaine et vérifiez-le
3. Récupérez votre clé API
4. Remplacez dans `.env.local` :
```env
RESEND_API_KEY=re_votre_cle_api
RESEND_FROM_EMAIL=noreply@votre-domaine.com
RESEND_CONTACT_EMAIL=contact@votre-domaine.com
```

#### 📊 Google Analytics
1. Créez une propriété GA4 sur [analytics.google.com](https://analytics.google.com)
2. Récupérez votre ID de mesure
3. Remplacez dans `.env.local` :
```env
NEXT_PUBLIC_GA_MEASUREMENT_ID=G-VOTRE_ID_MESURE
```

#### 🗄️ Base de Données
**Option 1 - Neon (Recommandé)**
1. Créez un compte sur [neon.tech](https://neon.tech)
2. Créez une base de données
3. Remplacez dans `.env.local` :
```env
DATABASE_URL="postgresql://user:pass@ep-xxx.us-east-1.aws.neon.tech/sds_production"
```

**Option 2 - Supabase**
1. Créez un projet sur [supabase.com](https://supabase.com)
2. Récupérez l'URL de connexion
3. Remplacez dans `.env.local` :
```env
DATABASE_URL="postgresql://postgres:pass@db.xxx.supabase.co:5432/postgres"
```

### ✅ 2. Sécurité

#### 🔐 Générer de Nouveaux Secrets
```bash
# Générer une clé NextAuth
openssl rand -base64 32

# Ou avec Node.js
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

#### 🛡️ Variables de Sécurité
```env
NEXTAUTH_SECRET=votre_nouveau_secret_genere
DEBUG=false
NEXT_TELEMETRY_DISABLED=1
DISABLE_EMAILS=false
STRIPE_TEST_MODE=false
```

### ✅ 3. Base de Données

#### 📦 Migration Prisma
```bash
# Générer le client Prisma
npx prisma generate

# Appliquer les migrations
npx prisma migrate deploy

# Seeder les données (optionnel)
npx prisma db seed
```

### ✅ 4. Build et Déploiement

#### 🏗️ Test Local
```bash
# Build de production
npm run build

# Test du build
npm start
```

#### 🚀 Déploiement Vercel (Recommandé)
1. Connectez votre repo GitHub à Vercel
2. Ajoutez toutes les variables d'environnement dans Vercel
3. Déployez automatiquement

#### 🚀 Déploiement Netlify
1. Connectez votre repo à Netlify
2. Configurez les variables d'environnement
3. Définissez la commande de build : `npm run build`

### ✅ 5. Configuration Domaine

#### 🌐 DNS
1. Pointez votre domaine vers votre hébergeur
2. Configurez les enregistrements DNS
3. Activez HTTPS/SSL

#### 📧 Email (si utilisation de Resend)
1. Ajoutez les enregistrements DNS pour votre domaine
2. Vérifiez le domaine dans Resend
3. Testez l'envoi d'emails

### ✅ 6. Monitoring

#### 📊 Analytics
- Vérifiez que Google Analytics fonctionne
- Testez les événements de conversion

#### 🐛 Erreurs
- Configurez Sentry pour le monitoring d'erreurs (optionnel)
- Surveillez les logs de votre hébergeur

### ✅ 7. Tests Finaux

#### 🧪 Tests Fonctionnels
- [ ] Navigation du site
- [ ] Formulaire de contact
- [ ] Calculateur France Num
- [ ] Paiements Stripe
- [ ] Emails de confirmation
- [ ] Responsive mobile

#### 💳 Tests Paiements
- [ ] Paiement par carte (mode test d'abord)
- [ ] Webhooks Stripe
- [ ] Emails de confirmation de commande

## 🆘 Support

### 📞 Contacts Utiles
- **Stripe Support** : [support.stripe.com](https://support.stripe.com)
- **Resend Support** : [resend.com/support](https://resend.com/support)
- **Vercel Support** : [vercel.com/support](https://vercel.com/support)

### 🔧 Dépannage Courant

#### Erreur Base de Données
```bash
# Réinitialiser la base
npx prisma migrate reset
npx prisma generate
```

#### Erreur Build
```bash
# Nettoyer le cache
rm -rf .next
npm run build
```

#### Erreur Stripe
- Vérifiez que les webhooks sont configurés
- Testez avec les cartes de test Stripe

## 🎉 Félicitations !

Votre site SDS est maintenant en production ! 🚀

N'oubliez pas de :
- Surveiller les performances
- Sauvegarder régulièrement
- Mettre à jour les dépendances
- Renouveler les certificats SSL

