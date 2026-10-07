# Deja buketi: ručni koraci

1. **Firebase: APNs ključ za iOS aplikaciju**
   Project settings → Cloud Messaging → iOS aplikacija rs.dejabuketi.app → upload istog .p8 ključa (Key ID i Team ID kao za Lumen), za Development i Production.

2. **Supabase: dozvoli povratak sa prijave**
   Authentication → URL Configuration → Redirect URLs → dodaj rs.dejabuketi.app://auth-callback

3. **Apple Developer: Bundle ID**
   Identifiers → + → App IDs → Explicit: rs.dejabuketi.app. Uključi Push Notifications i Sign in with Apple.

4. **Supabase: Apple prijava za novi bundle**
   Authentication → Providers → Apple → Client IDs: dodaj rs.dejabuketi.app (zarezom, pored postojećih).

5. **Google prijava na iOS-u**
   Google Cloud → Credentials → Create OAuth client → iOS, bundle rs.dejabuketi.app. Client ID upiši u kreator (Podaci → Tehničko) i generiši ponovo, ili ga sam upiši u src/lib/nativeAuth.js i Info.plist.

6. **App Store Connect: nova aplikacija**
   My Apps → + → New App, bundle rs.dejabuketi.app. Tekstovi su u prodavnice/app-store.txt, napomene za pregled u prodavnice/apple-pregled.txt.

7. **Play Console: nova aplikacija**
   Create app → Deja buketi. Tekstovi u prodavnice/google-play.txt, ikonica i naslovna slika u prodavnice/. Potpiši AAB istim upload ključem ili napravi novi za ovu aplikaciju.

8. **Build i slanje**
   Android: Android Studio → Generate Signed Bundle. iOS: kreator → Napravljene aplikacije → iOS build (u oblaku, bez Maca). Pre prvog builda moraju da postoje Bundle ID i aplikacija u App Store Connect.
