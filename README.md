# Project: Web Browser Simulation with Tabs and History

## Overview

This project simulates the architecture of a simplified **web browser**, inspired by the behaviour of modern browsers. The goal is to build a C application that:
- supports navigation between web pages
- manages **multiple tabs** simultaneously
- maintains **independent browsing history** for each tab

## Components

### Web Page

A web page is represented using a structure that includes:
- `ID` — an integer identifier
- `URL` — a string of up to 50 characters
- `description` — a variable-length string ending with a newline (`\n`)

Each time a new tab is created, a **default page** is loaded, always containing:
- `ID: 0`
- `URL: https://acs.pub.ro/`
- `Description: Computer Science`

### Web Tab

A tab is defined by a structure that contains:
- a **unique ID**
- a pointer to the **current web page**
- two stacks to manage navigation history:
  - `BACKWARD` — holds pages visited before the current page
  - `FORWARD` — holds pages visited after going back

All tabs are managed using a **circular doubly linked list with a sentinel node**. A pointer to the **currently active tab** is maintained to ensure easier interaction for basic operations in the browser.

### Web Browser

The browser is the main structure and includes:
- a list of all tabs
- a pointer to the currently active tab
- functionality for:
  - opening new tabs
  - switching between tabs
  - visiting new pages
  - navigating backward and forward in history

At startup, the browser contains a **default tab** (`ID: 0`) that loads the **default page**.
