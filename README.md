# Nature's Cafe: live ordering (Firebase)

Files
- `public/index.html`: the customer menu (QR codes open this)
- `public/staff.html`: the staff dashboard (login required)
- `firestore.rules`: the security rules
- `firebase.json`: hosting settings

## 1. In the Firebase console (project cafe-menu-289b7)
1. **Build > Firestore Database > Create database.** Choose production mode and a location close to you (for example, Mumbai, asia-south1).
2. **Build > Authentication > Get started > Email/Password > Enable.**
3. **Authentication > Users > Add user.** Create the owner account (and one for each staff member).
4. **Authentication > Settings > User actions:** untick **Enable create (sign-up)**, so nobody else can make an account.
5. **Build > Hosting > Get started.**

## 2. Set who counts as staff
Open `firestore.rules` and replace `owner@example.com` and `staff@example.com` with the real emails from step 1.3.

## 3. Deploy (one time, then again after any change)
Install Node.js, then in a terminal inside this folder:

    npm install -g firebase-tools
    firebase login
    firebase deploy --only hosting,firestore --project cafe-menu-289b7

Your site will be at https://cafe-menu-289b7.web.app (menu) and https://cafe-menu-289b7.web.app/staff.html (staff).

## 4. Make the table QR codes
Open `/staff.html`, sign in, tap **Table QR codes**, set the number of tables, and print.

## Changing the menu
Edit the list that starts with `const D=` in `public/index.html`, then deploy again.
