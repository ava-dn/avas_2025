---
layout: post
title: Sprint 3 Team Plan	
permalink: /sprint_3_team_plan
comments: true
---

# 🛒 D'nero Store Project Overview

This project aims to create an **interactive online chat room** where students can connect and buy their favorite items at the **D'nero Store**. By promoting new items and fostering communities around shared interests, students can engage with others who enjoy similar items and products.

---

## 🎉 **Key Innovation**
The project’s unique feature is its **community-building approach**. When students select items they're interested in, they’re added to **groups (chat communities)** with others who like the same items. This feature enhances user interaction by creating spaces for sharing images and discussing newly available items.

---

## 🛠️ **Key Features**
- **Activity Chatroom**: A designated space where students share opinions on items sold at the **Dinero Store**.
- **Community Matching**: Automatic group chat creation based on item preferences.

---

## 🚨 **Moderator Rules**
- Be **kind and respectful** to everyone in the forum.
- Keep comments **polite**; inappropriate or mean comments will be removed.
- Only discuss **D'nero Store** items.
- **No advertising** for other stores or schools (like Westview).
- **Have fun** sharing your opinions!

---

## 🍭 **Nighthawk Dinero Store** (Candy Showcase Page)

This page highlights the fun and interactive experience for students to browse and discuss **D'nero Store** items. The purpose is to create an engaging chat room specifically for **Del Norte High School** students, with a focus on the **D’Nero Store**.

![Nighthawk D'nero Store Visual](https://github.com/user-attachments/assets/561f05f0-281e-4d26-a631-75fcbf61931e)

---

## 📊 **Data to Capture in the Chat Room**

| Data                | Description                             |
|---------------------|-----------------------------------------|
| **Likes on posts**  | Number of likes each item post receives |
| **Comments**        | User-generated comments on items        |

---

## 🖥️ **Coding Work (flocker_frontend)**

```html
<img src="{{ site.baseurl }}/images/dnerostore/Dnero_Store_Header.png" alt="Dnero Store Header" style="width: 100%; height: auto;">
<h2><a href="{{ site.baseurl }}/dnerostore-mod/" class="mod-rules-button"> Mod Rules </a></h2> 

<details>
  <summary style="color: white;">Room Details</summary>
  <p style="color: white;">Discuss your favorite D'Nero store items here!</p>
</details>

<div class="container">
  <div class="category-box">
    <!-- Food and Drink Category -->
    <div class="category-row" onclick="toggleItems('food-drink-items')">
      <h3>Food and Drink</h3>
      <div id="food-drink-items" class="item-list-container" style="display: none;">
        <p>Please select your favorite item from this list:</p>
        <div class="item-list">
          <button onclick="selectItem(this, 'most', 'Food and Drink')" data-channel-id="28">Trail Mix</button>
          <button onclick="selectItem(this, 'most', 'Food and Drink')" data-channel-id="28">Nutella</button>
          <button onclick="selectItem(this, 'most', 'Food and Drink')" data-channel-id="28">Famous Amos</button>
          <button onclick="selectItem(this, 'most', 'Food and Drink')" data-channel-id="28">Chips</button>
          <button onclick="selectItem(this, 'most', 'Food and Drink')" data-channel-id="28">Sports Drinks</button>
          <button onclick="selectItem(this, 'most', 'Food and Drink')" data-channel-id="28">Fruit Snacks</button>
          <button onclick="selectItem(this, 'most', 'Food and Drink')" data-channel-id="28">Water</button>
          <button onclick="selectItem(this, 'most', 'Food and Drink')" data-channel-id="28">Pizza</button>
        </div>
        <p>Please select your LEAST favorite item from this list:</p>
        <div class="item-list">
          <button onclick="selectItem(this, 'least', 'Food and Drink')" data-channel-id="28">Trail Mix</button>
          <button onclick="selectItem(this, 'least', 'Food and Drink')" data-channel-id="28">Nutella</button>
          <button onclick="selectItem(this, 'least', 'Food and Drink')" data-channel-id="28">Famous Amos</button>
          <button onclick="selectItem(this, 'least', 'Food and Drink')" data-channel-id="28">Chips</button>
          <button onclick="selectItem(this, 'least', 'Food and Drink')" data-channel-id="28">Sports Drinks</button>
          <button onclick="selectItem(this, 'least', 'Food and Drink')" data-channel-id="28">Fruit Snacks</button>
          <button onclick="selectItem(this, 'least', 'Food and Drink')" data-channel-id="28">Water</button>
          <button onclick="selectItem(this, 'least', 'Food and Drink')" data-channel-id="28">Pizza</button>
        </div>
      </div>
    <div id="food-drink-posts" class="category-posts"></div>
    </div>
  <!-- Spirit Category -->
  <div class="category-box">
  <div class="category-row" onclick="toggleItems('spirit-items')">
    <h3>Spirit</h3>
    <div id="spirit-items" class="item-list-container" style="display: none;">
      <p>Please select your favorite item from this list:</p>
      <div class="item-list">
        <button onclick="selectItem(this, 'most', 'Spirit')" data-channel-id="29">Morning Song</button>
        <button onclick="selectItem(this, 'most', 'Spirit')" data-channel-id="29">DNHS T-shirt</button>
        <button onclick="selectItem(this, 'most', 'Spirit')" data-channel-id="29">1 Pom Pom</button>
      </div>
      <p>Please select your LEAST favorite item from this list:</p>
      <div class="item-list">
        <button onclick="selectItem(this, 'least', 'Spirit')" data-channel-id="29">Morning Song</button>
        <button onclick="selectItem(this, 'least', 'Spirit')" data-channel-id="29">DNHS T-shirt</button>
        <button onclick="selectItem(this, 'least', 'Spirit')" data-channel-id="29">1 Pom Pom</button>
      </div>
    </div>
    <div id="spirit-posts" class="category-posts"></div>
  </div>

  <!-- Limited Edition Category -->
  <div class="category-box">
  <div class="category-row" onclick="toggleItems('limited-edition-items')">
    <h3>Limited Edition</h3>
    <div id="limited-edition-items" class="item-list-container" style="display: none;">
      <p>Please select your favorite item from this list:</p>
      <div class="item-list">
        <button onclick="selectItem(this, 'most', 'Limited Edition')" data-channel-id="30">Candy</button>
        <button onclick="selectItem(this, 'most', 'Limited Edition')" data-channel-id="30">Squishmallow mini</button>
        <button onclick="selectItem(this, 'most', 'Limited Edition')" data-channel-id="30">Starbucks SDSU Tumbler</button>
      </div>
      <p>Please select your LEAST favorite item from this list:</p>
      <div class="item-list">
        <button onclick="selectItem(this, 'least', 'Limited Edition')" data-channel-id="30">Candy</button>
        <button onclick="selectItem(this, 'least', 'Limited Edition')" data-channel-id="30">Squishmallow mini</button>
        <button onclick="selectItem(this, 'least', 'Limited Edition')" data-channel-id="30">Starbucks SDSU Tumbler</button>
      </div>
    </div>
    <div id="limited-edition-posts" class="category-posts"></div>

  </div>
  <!-- Gift Cards Category -->
  <div class="category-box">
  <div class="category-row" onclick="toggleItems('gift-card-items')">
    <h3>Gift Cards</h3>
    <div id="gift-card-items" class="item-list-container" style="display: none;">
      <p>Please select your favorite item from this list:</p>
      <div class="item-list">
        <button onclick="selectItem(this, 'most', 'Gift Cards')" data-channel-id="31">Chik-fil-a</button>
        <button onclick="selectItem(this, 'most', 'Gift Cards')" data-channel-id="31">Canes</button>
      </div>
      <p>Please select your LEAST favorite item from this list:</p>
      <div class="item-list">
        <button onclick="selectItem(this, 'least', 'Gift Cards')" data-channel-id="31">Chik-fil-a</button>
        <button onclick="selectItem(this, 'least', 'Gift Cards')" data-channel-id="31">Canes</button>
      </div>
    </div>
    <div id="gift-card-posts" class="category-posts"></div>

```

## Evidence of research and look-a-like ideas from Reddit, Pinterest, etc. Showing research.
![image](https://github.com/user-attachments/assets/64cbffb9-83c3-4cdf-b865-58d2b4eed4ea)
