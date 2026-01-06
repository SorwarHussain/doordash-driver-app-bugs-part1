# doordash-driver-app-bugs-part1
Documented issues and bug reports discovered while using the DoorDash Driver app in production.

# Bug Report
**Title:** “Something went wrong” shown after completing delivery steps for combined orders in DoorDash Driver app

## Description
When delivering **combined (stacked) orders** in the DoorDash Driver app, the delivery flow completes successfully, but after finishing the delivery steps for each order, the app displays an error message saying **“Something went wrong”** instead of a success confirmation. This issue occurs consistently for combined deliveries and does not reflect the actual delivery status.

---

## Steps to Reproduce
1. Open the **DoorDash Driver (Dasher)** app.
2. Accept **two combined (stacked) food delivery orders**.
3. Pick up both orders from the restaurant(s).
4. Navigate to the delivery location(s).
5. Complete the delivery steps for the first order (e.g., confirm delivery, take photo if required).
6. Observe the message shown after completing the delivery.
7. Repeat the same steps for the second order.

---

## Expected Behavior
- After completing delivery steps for each order, the app should display a **successful delivery confirmation** (e.g., “Delivery completed”).
- No error message should be shown when the delivery is completed correctly.

---

## Actual Behavior
- After completing delivery steps, the app displays **“Something went wrong.”**
- The error message appears **every time** for combined deliveries.
- The delivery appears to be completed, but the UI incorrectly reports an error.

---

## Frequency
- Occurs **100% of the time** for combined food deliveries.

---

## Environment
- **Application:** DoorDash Driver (Dasher) app
- **Platform:** Android
- **App Version:** 8.61.6
- **Network:** Mobile data 
---

## Impact
- Creates confusion for drivers, who may think the delivery failed.
- Negatively affects driver experience during stacked deliveries.

---

## Additional Notes
- This issue does not appear to occur with **single (non-combined) deliveries**.

---

## Attachments
- Screenshots showing the error message after completing delivery.


![Screenshot_20260105_230131_Video Player](https://github.com/user-attachments/assets/d894873f-72c1-47f5-8d9b-2d417ec0374a)
![Screenshot_20260105_230108_Video Player](https://github.com/user-attachments/assets/d492e435-7a6c-4824-a850-51edde172e87)
![Screenshot_20260105_230058_Video Player](https://github.com/user-attachments/assets/1246ceb0-8b5d-42f1-baa2-b57d09769f9b)

---

## Possible Root Cause (Speculative)
- Backend response succeeds, but frontend fails to handle the success state for combined orders.
- Incorrect error handling or state management for stacked delivery completion.

