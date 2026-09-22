# Streakly-habit-tracking-app

> **OPSC6312 Portfolio of Evidence — Parts 1 & 2**  
> **Authors:** Tumisho Kokhutja (ST10446195), Mzamo Richmond Ndlovu (ST10455453), Lesego Ayanda Mathe (ST10440650)[cite: 1, 2]

---

## 📌 Executive Summary
Streakly is an offline-first, REST API–connected habit-tracking application built for Android 10+ (API Level 29+)[cite: 1]. It addresses key limitations identified across market-leading habit trackers:
* **Loop Habit Tracker:** Offers complete offline privacy and speed, but lacks cross-device synchronization and gamification[cite: 2].
* **Habitica:** Delivers high retention via gamification and multi-device sync, but requires a constant internet connection and suffers from visual screen clutter[cite: 1, 2].
* **Habo:** Provides clear visual calendar heat-maps, but offers limited statistical/analytical depth[cite: 2].

Streakly combines the best elements of all three: **Loop’s offline reliability**, **Habitica’s RESTful cloud synchronization and motivation**, and **Habo’s clean calendar heat-maps**, while maintaining a simple, uncluttered interface built with Material Design components[cite: 1, 2].

---

## 📖 User Guide (How to Use Streakly)

### 1. Getting Started & Account Authentication
1. **Launch the App:** Open **Streakly** on your Android device[cite: 1].
2. **Sign Up or Log In:**
   * **Email & Password:** Enter your email address and password, then tap **Submit**[cite: 1].
   * **Single Sign-On (SSO):** Tap **Continue with Google** to automatically register or log in using your Google credentials[cite: 1].
3. **Session Security:** Your account remains securely logged in across app launches using encrypted device storage (`EncryptedSharedPreferences`)[cite: 1, 2].

---

### 2. Creating and Managing Habits
1. **Navigate to Home:** Tap the **Home** tab on the bottom navigation bar[cite: 1].
2. **Add a New Habit:**
   * Tap the **+ Add Habit** button at the bottom of the Home screen[cite: 1].
   * Enter the **Habit Name** (e.g., *"Drink Water"*, *"Read 10 Pages"*, *"Meditate"*)[cite: 1].
   * Select the **Frequency**:
     * **Daily:** Every day[cite: 1].
     * **Specific Days:** Choose custom days of the week[cite: 1].
     * **Interval:** Set repeating custom day intervals[cite: 1].
   * Choose a **Reminder Time** for daily notifications[cite: 1].
   * Select a **Color / Icon** theme to personalize the habit card[cite: 1].
   * Tap **Save Habit**[cite: 1].
3. **Edit or Archive a Habit:**
   * Tap on any habit card from the Home screen or Calendar view to adjust its settings, update reminder times, or archive the habit[cite: 1].

---

### 3. Daily Completion Logging & Streaks
1. **View Today's Habits:** The **Home** screen displays all habits scheduled for completion today[cite: 1].
2. **Log a Completion:**
   * Tap the completion checkmark circle next to a habit to mark it as **Done**[cite: 1].
   * The UI updates instantly (<200ms), increasing your current **Streak Counter** and awarding **Gamification Points**[cite: 1].
3. **Undo Log Entry:** Tap the completed checkmark circle again if you need to uncheck a habit[cite: 1].

---

### 4. Viewing Habit History & Calendar Heat-Map
1. **Access Calendar View:** Tap the **Calendar** tab on the bottom navigation bar or select a specific habit from the Home screen[cite: 1].
2. **Analyze Heat-Map:**
   * Green grid squares indicate days where the habit was successfully completed[cite: 1, 2].
   * Light/Gray squares indicate missed or non-scheduled days[cite: 1].
3. **Check Streak Metrics:** View your **Current Active Streak** and **Longest-Ever Streak** at a glance[cite: 1].
4. **Add Daily Notes:** Attach free-text reflection notes to any specific calendar date[cite: 1].

---

### 5. Gamification, Points & Redeeming Rewards
1. **Access Rewards Screen:** Tap the **Rewards** tab on the bottom navigation bar[cite: 1].
2. **Monitor Level & Points:** View your accumulated total points and current level progress bar at the top of the screen[cite: 1].
3. **Earn Badges:** Unlock visual milestone badges as you maintain long-term streaks[cite: 1].
4. **Redeem Rewards:**
   * Define custom personal rewards (e.g., *"Coffee Treat - 50 pts"*, *"Movie Night - 120 pts"*, *"Rest Day Pass - 30 pts"*)[cite: 1].
   * When you have enough points, tap on a reward item to redeem and spend your points[cite: 1].

---

### 6. Offline Usage & Data Synchronization
1. **Logging Offline:** You can view, add, or complete habits without an internet connection[cite: 1, 2]. All changes are stored safely in the local Room database[cite: 1, 2].
2. **Automatic Background Sync:** Once internet connection is restored, Streakly automatically pushes your queued offline logs to the cloud REST API in a single batch[cite: 1, 2].
3. **Manual Backup & Sync:** Open **Profile & Settings** and tap **Backup & Sync** to force a manual cloud synchronization at any time[cite: 1].

---

### 7. Customization & App Settings
Navigate to the **Profile** tab to manage app preferences[cite: 1]:
* **Dark Mode:** Toggle dark theme on/off for comfortable nighttime viewing[cite: 1, 2].
* **Language Selector:** Switch instantly between **English**, **isiZulu**, and **Setswana** without restarting the app[cite: 1].
* **Reminders:** Adjust global notification preferences[cite: 1].
* **Export Data:** Download your entire habit history as a local file (CSV/JSON) for data portability[cite: 1, 2].
* **Log Out:** Securely sign out of your account[cite: 1].

---

## ✨ Features & Functional Requirements
* **Authentication:** Firebase Authentication with email/password and Single Sign-On ("Continue with Google")[cite: 1]. Session tokens are stored locally via `EncryptedSharedPreferences`[cite: 1, 2].
* **Habit Management:** Create habits with flexible frequencies (daily, specific weekdays, repeating intervals), reminder times, and color/icon tags[cite: 1].
* **Daily Logging & Streaks:** One-tap completion on the Home screen recalculating current and longest streaks[cite: 1].
* **Calendar Heat-Map:** Dedicated monthly calendar view for each habit showing completed, missed, or upcoming days[cite: 1, 2].
* **Gamification:** Points system awarding experience per completion, calculated user levels, and redeemable rewards[cite: 1, 2].
* **Reminders & Push Alerts:** Local reminders scheduled via `WorkManager` and `AlarmManager`[cite: 1, 2]. Server-side nightly checks trigger real-time FCM push notifications before streaks break[cite: 1].
* **Multi-Language & Customization:** Switch between English, isiZulu, and Setswana instantly in Settings, along with Dark Mode toggle support[cite: 1].

---

## 📱 Screen Navigation & UI Structure

Streakly uses a clean Bottom Navigation Bar with four primary tabs[cite: 1]:
1. **Home (Today's Habits):** Displays habits due today with one-tap completion checkmarks, active streak count, current user level, and quick access to add new habits[cite: 1].
2. **Calendar (Habit Detail):** Interactive monthly heat-map grid showing completed/missed history, current/longest streaks, and daily notes[cite: 1].
3. **Rewards:** Uncluttered overview of total points, user level, available badges, and redeemable custom reward items[cite: 1].
4. **Profile & Settings:** Account management, Dark Mode toggle, language selector, manual cloud backup & sync trigger, and CSV/JSON data export[cite: 1].
