---
layout: post
title: "​Fixing False Warnings on my Air 75"
date: 2026-08-12
categories:
  - fpv
tags:
  - tinywhoop
  - betafpv
---


If you're flying a **BetaFPV Air 75 II** or another micro FPV quad and your OSD is showing incorrect battery warnings, calibrating the current scale in Betaflight may solve the problem.

I've been practicing with my BetaFPV Air 75 II for about two months. Despite countless crashes, this little quad is still flying strong! Recently, however, I noticed something strange: even with a freshly charged battery, the OSD was already showing **"LANDING NOW."**

The problem turned out to be inaccurate voltage and current readings.

In this guide, I'll walk you through the process of calibrating the **current scale** in Betaflight so your mAh readings are more accurate.

## Why Calibrate the Current Scale?

Betaflight uses the current scale setting to estimate how much battery capacity you've consumed during a flight.

If the scale is incorrect, the mAh reading shown on your OSD can be significantly different from the amount of capacity you've actually used. This can lead to inaccurate battery warnings and make it harder to know when it's time to land.

The good news is that calibrating it only requires a flight, a battery charger, and three numbers.

## What You'll Need

Before starting, make sure you have:

- Your FPV drone and a fully charged battery  
- A battery charger that displays the amount of mAh charged  
- Betaflight Configurator  
- The current scale value from your Betaflight settings  

You'll need these **three numbers**:

1. The mAh reported by Betaflight after your flight  
2. The mAh put back into the battery by your charger  
3. Your current current-scale setting in Betaflight  

## Step 1: Fly the Battery

Start with a **fully charged battery**.

Fly normally until the battery reaches approximately **3.3 V per cell**. Once you land, immediately check your OSD and write down the amount of mAh used.

In my case:

> **OSD mAh used: 232 mAh**

It's important to record the value immediately after landing so you have an accurate reading from that flight.

## Step 2: Recharge the Same Battery

Next, put the **same battery** on your charger and charge it back to 100%.

Most chargers will show how many mAh were put back into the battery during the charging process.

For my battery, the charger reported:

> **Charger mAh: 336 mAh**

This gives us a real-world reference for how much capacity was actually consumed.

## Step 3: Check Your Current Scale

Now connect your drone to Betaflight Configurator.

Navigate to:

**Power & Battery → Current Meter / Current Sensor settings**

Find the **Current Scale** value and write it down.

My original setting was:

> **Old Current Scale: 750**

At this point, we have all three numbers needed for the calibration.

## Step 4: Calculate the New Current Scale

Now we can calculate the corrected current scale.

The formula is:

**New Current Scale = Old Current Scale × (OSD mAh Used ÷ Charger mAh)**

Using my numbers:

- Old Current Scale = **750**  
- Charger mAh = **336 mAh**  
- OSD mAh Used = **232 mAh**  

So:

**New Current Scale = 750 × (232 ÷ 336)**

This gives a new current-scale value of approximately:

> **New Current Scale ≈ 518**

The important thing is to use the actual values from **your own flight and charger** rather than copying my numbers.

## Step 5: Update Betaflight

Go back to the **Power & Battery** tab in Betaflight and replace your old current-scale value with the newly calculated value.

For my setup, I changed the value from:

**750 → approximately 518**

Click **Save** and you're ready to test the calibration.

## Testing the Calibration

After updating the current scale, I took the Air 75 II out for another flight.

The difference was immediately noticeable.

Looking at the DVR footage, the OSD was now showing much more reasonable battery information. The battery voltage remained steady, and the false **"LANDING NOW"** warnings were gone.

The current and mAh readings were now much closer to what I expected.

## Final Thoughts

Calibrating the current scale completely solved the inaccurate battery-reading issue on my BetaFPV Air 75 II.

If you're experiencing problems such as:

- Incorrect mAh readings  
- Battery warnings appearing too early  
- An OSD showing **"LANDING NOW"** when your battery is still relatively fresh  
- Current readings that don't match your actual battery usage  

then it's worth checking your **current scale** in Betaflight.

The process is simple: **fly, recharge, compare the numbers, calculate the new scale, and test again.**

Just remember that the exact calibration value will depend on your particular drone, battery, current sensor, and setup.

If this guide helped you, consider sharing it with another FPV pilot who might be dealing with the same problem.



