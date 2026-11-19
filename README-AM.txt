SAFETY 360 – የመጀመሪያ ሙሉ ፓኬጅ
=====================================

የፋይል አቀማመጥ
---------------
safety360_full_starter/
  firebase.json
  firestore.rules
  firestore.indexes.json
  storage.rules
  public/
    index.html
    manifest.json
    service-worker.js

አስፈላጊ ማስታወሻ
-----------------
1) የFirebase Web config በindex.html ውስጥ ከተሰጠው ፕሮጀክት ጋር ተያይዟል።
2) Firebase Web API key ብቻውን የደህንነት መከላከያ አይደለም። Security Rules መጫን ግዴታ ነው።
3) Firebase Console > Authentication > Sign-in method ውስጥ Email/Password አብሩ።
4) Firebase Console > Authentication > Users ውስጥ የመጀመሪያ Super Admin ተጠቃሚ ፍጠሩ።
5) የተፈጠረውን UID በFirestore > users > admin የሚባል document ውስጥ እንዲህ ያስገቡ:
   uid: "AUTH_USER_UID"
   role: "super_admin"
   active: true
   email: "admin@example.com"
   (uid የAuthentication UID መሆን አለበት።)
6) Firestore Database እና Storage ካልተፈጠሩ በFirebase Console ይፍጠሩ።
7) Firebase CLI በመጠቀም በፕሮጀክቱ ዋና ፎልደር ውስጥ:
   firebase login
   firebase use safety-360-8f4fe
   firebase deploy --only firestore:rules,firestore:indexes,storage
8) Hosting ለመጫን public ፎልደሩን ይጠቀሙ:
   firebase deploy --only hosting

GitHub Pages ከተጠቀሙ:
- public/index.html, public/manifest.json, public/service-worker.js ይዘቶችን
  ወደ repository root ያንቀሳቅሱ/ይቅዱ።
- GitHub Pages የFirestore/Storage Security Rules አያስተናግድም፤
  እነዚህ Firebase Console/CLI ውስጥ መጫን አለባቸው።

የደህንነት ወሰን
-----------------
- ህዝብ ሪፖርት ማስገባት ይችላል፤ ሪፖርቱ pending ይሆናል።
- ህዝብ የተፈቀዱ (approved) ሪፖርቶችን ብቻ ያነባል።
- Moderator ሪፖርቶችን ይመረምራል፤ የሰራተኛ መለያ መፍጠር አይችልም።
- Super Admin ሪፖርቶችን ማጥፋትና Moderator መመዝገብ ይችላል።
- የሰራተኛ Authentication መለያ በFirebase Console ወይም በተጠበቀ Admin SDK backend መፍጠር አለበት።
- SOS ቅጽ ሪፖርት ይመዘግባል፤ በራሱ የድንገተኛ ጥሪ አያደርግም።
- GPS በHTTPS እና በተጠቃሚ ፈቃድ ብቻ ይሰራል።
- ይህ የመጀመሪያ ማስጀመሪያ ፓኬጅ ነው፤ ከህዝብ ጋር ከመጠቀም በፊት በሙከራ አካባቢ ይፈትሹ።

የሚቀጥለው ስራ
----------------
- Firebase Console ውስጥ project setup እና admin provisioning
- የሪፖርት ክትትል ቁጥር ፍለጋ
- የካርታ እና የማሳወቂያ አገልግሎት
- ምትኬ፣ የግላዊነት ፖሊሲ እና የተቋማት የስራ ሂደት
