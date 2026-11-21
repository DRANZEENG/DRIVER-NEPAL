# Driver Nepal — zero-budget demo package

यो प्याकेज वेबसाइटको छुट्टै demo र Flutter Android/Web एपको source code हो।

## समावेश
- `website/index.html`: ब्राउजरमा चल्ने responsive demo वेबसाइट; जागिर खोजी, चालक प्रोफाइल, कम्पनी विज्ञापन र स्थानीय demo approval
- `lib/main.dart`: Flutter app source; Android र Flutter Web का लागि
- `web/index.html`: Flutter Web entry point
- `supabase/schema.sql`: प्रारम्भिक Supabase schema (अघिल्लो starter बाट समावेश)

## महत्वपूर्ण सीमा
यो **परीक्षण डेमो** हो, उत्पादन-तयार बहु-प्रयोगकर्ता सेवा होइन।
- वेबसाइट डेमोले डाटा प्रयोगकर्ताको आफ्नै ब्राउजरको localStorage मा मात्र राख्छ।
- Flutter डेमोमा डाटा एप खुला रहँदासम्मको स्थानीय state मा हुन्छ; एप बन्द गरेपछि हराउन सक्छ।
- वेबसाइट र Android बीच डाटा साझा हुँदैन।
- Admin डेमोमा वास्तविक प्रमाणीकरण/सर्भर सुरक्षा छैन। सार्वजनिक प्रयोगका लागि प्रयोग नगर्नुहोस्।
- नमुना जागिरहरू उदाहरण मात्र हुन्, वास्तविक vacancy होइनन्।
- OTP, वास्तविक आवेदन, कम्पनी प्रमाणीकरण, सुरक्षित Admin, privacy/terms, abuse prevention र RLS परीक्षण बाँकी छन्।
- `info@Independent.com` को स्वामित्व/सक्रियता पुष्टि भएको छैन। प्रयोग अघि पुष्टि गर्नुहोस्।

## वेबसाइट तुरुन्त हेर्ने
`website/index.html` फाइल Chrome मा खोल्नुहोस्। परीक्षणका लागि कम्प्युटरमा वा मोबाइलमा फाइल खोल्न सकिन्छ। वास्तविक सार्वजनिक वेबसाइट बनाउन static hosting मा deploy गर्नुपर्छ।

## Android एप चलाउने
Flutter SDK र Android Studio भएको कम्प्युटरमा:
```bash
flutter pub get
flutter run
```
APK:
```bash
flutter build apk --release
```
AAB:
```bash
flutter build appbundle --release
```
यो प्याकेजमा APK पहिल्यै बनेको छैन; Flutter build चलाउनुपर्नेछ।

## Flutter Web
```bash
flutter config --enable-web
flutter build web --release
```
नोट: standalone website demo `website/index.html` र Flutter Web build दुई अलग विकल्प हुन्।

## वास्तविक अनलाइन सेवा बनाउनुपर्ने चरण
1. Supabase परियोजना खोल्ने र schema समीक्षा गरेर मात्र लागू गर्ने।
2. Auth र database जोड्ने; SMS OTP ले शुल्क लाग्न सक्छ।
3. role assignment server-side बाट मात्र गर्ने; client बाट admin role दिनु हुँदैन।
4. RLS policies को driver/company/admin अलग-अलग खाताबाट सुरक्षा परीक्षण गर्ने।
5. निजी कागजात अपलोड सुविधा थप्नुअघि consent, retention र access policy तयार गर्ने।
6. privacy policy, terms, moderation/reporting, data deletion र backup व्यवस्था बनाउने।
7. परीक्षण सफल भएपछि मात्र सार्वजनिक hosting / Play Store मा प्रकाशन गर्ने।

## गोपनीयता
परीक्षणमा नागरिकता, लाइसेन्स फोटो, पासवर्ड वा संवेदनशील व्यक्तिगत कागजात नहाल्नुहोस्।
