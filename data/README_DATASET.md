# Fitrax User Evaluation Dataset (Replication Package)

This repository contains the anonymized replication dataset for the user experience and usability evaluation of the **Fitrax** intelligent fitness assistant mobile application ($N = 11$).

---

## Dataset Overview
* **File Name:** `fitrax_user_evaluation_dataset.csv`
* **Format:** Comma-Separated Values (CSV), Encoded in `UTF-8 with BOM` (compatible with Microsoft Excel, Python, R, Stata, and SPSS)
* **Sample Size ($N$):** 11 active gym attendees (Beginner, Intermediate, and Advanced)
* **Standard Likert Anchors (Questions Q2 to Q6):**
  * **1** = Strongly Disagree (کاملاً مخالفم)
  * **2** = Disagree (مخالفم)
  * **3** = Neutral / Moderate (نظری ندارم / خنثی)
  * **4** = Agree (موافقم)
  * **5** = Strongly Agree (کاملاً موافقم)

---

## Data Dictionary & Question Specification (کدبوک جامع متغیرها)

| # | Column Header in CSV | Question Type (نوع سوال) | Scoring Scale / Value Range (بازه و نحوه امتیازدهی) | Survey Question (Persian Verbatim) | English Meaning & Evaluation Concept |
| :-: | :--- | :---: | :---: | :--- | :--- |
| **1** | `Participant_ID` | Identifier | `P01` – `P11` | شناسه شرکت‌کننده | Unique anonymized respondent ID. |
| **2** | `Gender` | Demographic | `Male`, `Female` | جنسیت شما | Self-reported participant gender. |
| **3** | `Gym_Training_Experience` | Demographic | Categorical: <br>• `Beginner (< 1 year)`<br>• `Intermediate (1-3 years)`<br>• `Advanced (> 3 years)` | سطح تجربه تمرینی | Gym resistance training experience level. |
| **4** | `Q1_Logged_Workout_Session_Prior_to_Survey` | Screening Filter | Binary Choice:<br>• `Yes`<br>• `No` | پیش از تکمیل نظرسنجی: آیا از اپ فیت‌رکس استفاده کردید و یک جلسه‌ی تمرینی ایجاد و ثبت کرده‌اید؟ | Verification that the user completed and logged at least one full workout with Fitrax prior to evaluation (`Yes`). |
| **5** | `Q2_In_Workout_Set_And_Weight_Logging_Convenience_vs_Traditional_Methods` | 5-point Likert | Integer `[1 – 5]`<br>(1=Min, 5=Max) | ثبت اطلاعات حین تمرین (تیک زدن ست‌ها و تغییر وزنه‌ها) در فیت‌رکس، در مجموع تجربه‌ی راحت‌تری نسبت به روش‌های سنتی بود و اختلال چندانی در تمرکزم ایجاد نکرد. | **Logging Interface (Mean: 4.09 ± 0.70):** Evaluates if digital in-workout set/weight tracking was more convenient and less disruptive than paper or phone notes. |
| **6** | `Q3_Smart_Rest_Timer_Utility_And_Workout_Pacing` | 5-point Likert | Integer `[1 – 5]`<br>(1=Min, 5=Max) | تایمر هوشمند برنامه (که زمان استراحت بین ست‌ها و حرکات را جداگانه محاسبه می‌کند)، ابزار مفیدی بود و به حفظ ریتم و زمان‌بندی تمرینم کمک کرد. | **Smart Rest Timer (Mean: 3.73 ± 1.27):** Evaluates utility of independent inter-set and inter-exercise timers in maintaining workout rhythm and pacing. |
| **7** | `Q4_AI_Assistant_Exercise_Alternatives_And_QnA_Satisfaction` | 5-point Likert | Integer `[1 – 5]`<br>(1=Min, 5=Max) | از عملکرد دستیار هوشمند در حین تمرین رضایت دارم؛ حرکات جایگزین و پیشنهادهایی که ارائه داد ایمن، مرتبط و برایم کاربردی بودند. همچنین پاسخ به سوالاتم حین تمرین را به‌خوبی می‌داد. | **AI Assistant (Mean: 3.64 ± 1.29):** Assesses user satisfaction with conversational AI suggestions, safe substitute exercises, and in-workout Q&A support. |
| **8** | `Q5_Gamification_Motivational_Feedback_And_Sense_of_Achievement` | 5-point Likert | Integer `[1 – 5]`<br>(1=Min, 5=Max) | ویژگی‌های جذاب برنامه (مثل انیمیشن پایان تمرین، فرم ثبت میزان خستگی و پیام‌های انگیزشی) تاثیر مثبتی روی حس موفقیت من داشت و برای ادامه‌ی تمریناتم انگیزه‌بخش بود. | **Gamification & Adherence (Mean: 4.36 ± 0.50):** Evaluates motivational cues, completion animations, and perceived sense of accomplishment. |
| **9** | `Q6_Future_Intention_to_Use_Fitrax_as_Primary_Workout_Assistant` | 5-point Likert | Integer `[1 – 5]`<br>(1=Min, 5=Max) | تمایل دارم در آینده نیز به جای روش‌های قبلی، از فیت‌رکس به عنوان دستیار تمریناتم استفاده کنم. | **Intention to Adopt (Mean: 4.09 ± 0.70):** Behavioral willingness to adopt Fitrax as a routine workout companion. |
| **10** | `Q7_Suggested_Improvement_or_Feature_Change_EN` | Open-Ended Text | Free text (English)<br>(`N/A` if empty) | اگر بخواهید یک ویژگی را در Fitrax تغییر داده یا بهبود ببخشید، آن ویژگی چیست؟ | Qualitative user suggestions and feature requests translated into professional English. |
| **11** | `Q7_Suggested_Improvement_or_Feature_Change_FA` | Open-Ended Text | Free text (Persian)<br>(`N/A` if empty) | اگر بخواهید یک ویژگی را در Fitrax تغییر داده یا بهبود ببخشید، آن ویژگی چیست؟ | Original verbatim qualitative feedback in Persian. |
| **12** | `Survey_Completion_Time_Seconds` | System Metric | Integer $\ge 0$ (Seconds) | مدت زمان تکمیل پرسشنامه | Total time spent by the respondent completing the questionnaire (in seconds). |

---

## Statistical Summary Table ($N = 11$)

| # | Evaluated Dimension | Question Ref | Mean ($\bar{x}$) | Sample SD ($s$) | Median | Observed Range |
| :-: | :--- | :---: | :---: | :---: | :---: | :---: |
| **1** | **Gamification & Motivation** | `Q5` | **4.36** | **0.50** | 4.0 | [4, 5] |
| **2** | **Workout Logging Interface** | `Q2` | **4.09** | **0.70** | 4.0 | [3, 5] |
| **3** | **Long-term Intention to Use** | `Q6` | **4.09** | **0.70** | 4.0 | [3, 5] |
| **4** | **Smart Rest Timer** | `Q3` | **3.73** | **1.27** | 4.0 | [1, 5] |
| **5** | **In-Workout AI Assistant** | `Q4` | **3.64** | **1.29** | 4.0 | [1, 5] |
| — | **Overall System Usability** | `Q2–Q6` | **3.98** | **0.95** | 4.0 | [1, 5] |
