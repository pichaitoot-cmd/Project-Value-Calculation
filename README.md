# Project-Value-Calculation
WHETHER
# โครงสร้างโปรเจคคำนวณค่า
You said: สร้างรูปแบบโครงสร้างโปรเจคในแบบค่าเฉลี่ยพร้อมรายการระบบและฟิวเจอร์แสดงผล
# สร้างรูปแบบโครงสร้างโปรเจคในแบบค่าเฉลี่ยพร้อมรายการระบบและฟิวเจอร์แสดงผล
#  เพื่อสร้างโครงสร้างโปรเจคในรูปแบบ “ค่าเฉลี่ย” พร้อมรายการระบบ (System) และฟีเจอร์ (Feature) ที่แสดงผลได้ชัดเจน
# เพื่อสร้างโครงสร้างโปรเจคในรูปแบบ “ค่าเฉลี่ย” พร้อมรายการระบบ (System) และฟีเจอร์ (Feature) ที่แสดงผลได้ชัดเจน สามารถออกแบบโครงสร้างและโฟลเดอร์ดังนี้ (ตัวอย่างโครงการเว็บแอปคำนวณค่าเฉลี่ย):

Code
project-average-calculator/
│
├── README.md                    # อธิบายโครงการและวิธีการใช้งาน
├── package.json                 # ข้อมูล dependencies (ถ้าใช้ Node.js)
├── public/                      # ไฟล์ static เช่น index.html, รูปภาพ
│   └── index.html
├── src/
│   ├── components/              # ส่วนประกอบ UI เช่น ตาราง, ฟอร์ม
│   │   ├── AverageTable.js      # ตารางแสดงผลค่าเฉลี่ย
│   │   ├── InputForm.js         # ฟอร์มกรอกข้อมูล
│   │   └── FeatureList.js       # แสดงรายการฟีเจอร์ทั้งหมด
│   ├── systems/                 # ระบบหลัก (business logic)
│   │   ├── calculation.js       # ฟังก์ชันคำนวณค่าเฉลี่ย
│   │   └── validation.js        # ฟังก์ชันตรวจสอบข้อมูล
│   ├── features/                # ฟีเจอร์ย่อย
│   │   ├── addItem.js           # เพิ่มข้อมูล
│   │   ├── removeItem.js        # ลบข้อมูล
│   │   ├── editItem.js          # แก้ไขข้อมูล
│   │   └── exportResult.js      # ส่งออกผลลัพธ์
│   ├── App.js                   # Root component
│   └── index.js                 # Entry point
├── tests/                       # Unit test
│   ├── calculation.test.js
│   └── validation.test.js
└── .gitignore

#รายการระบบ (Systems)
ระบบคำนวณค่าเฉลี่ย (calculation.js): รับข้อมูลและคำนวณค่าเฉลี่ย
# ระบบตรวจสอบข้อมูล (validation.js): ตรวจสอบ ความถูกต้องก่อนคำนวณ
#รายการฟีเจอร์ (Features)
# เพิ่มข้อมูล (addItem.js): เพิ่มข้อมูลใหม่เข้ารายการ
ลบข้อมูล (removeItem.js): ลบข้อมูลออกจากรายการ
แก้ไขข้อมูล (editItem.js): แก้ไขข้อมูลที่มีอยู่แล้ว
แสดงผลลัพธ์ (AverageTable.js): แสดงผลค่าเฉลี่ย
ส่งออกผลลัพธ์ (exportResult.js): ส่งออกผลลัพธ์เป็นไฟล์ (CSV, PDF ฯลฯ)
# ตัวอย่างแสดงผล
หน้าเว็บมีฟอร์มให้กรอกข้อมูล
มีตารางแสดงข้อมูลและค่าเฉลี่ย
มีปุ่มเพิ่ม ลบ แก้ไข และส่งออกผลลัพธ์

#ตัวอย่างโค้ดหรือรายละเอียดโฟลเดอร์ใดเพิ่มเติม 

# ขอรูปแบบแสดงตัวอย่างเป็นโค้ด
ขอรูปแบบแสดงตัวอย่างเป็นโค้ด
Copilot said: ตัวอย่างโครงสร้างโปรเจคสำหรับ “คำนวณค่าเฉลี่ย” พร้อมระบบและฟีเจอร์ (Node.js + React): ```plaintext project-average-calculator/ │ ├── README.md ├──
ตัวอย่างโครงสร้างโปรเจคสำหรับ “คำนวณค่าเฉลี่ย” พร้อมระบบและฟีเจอร์ (Node.js + React):

plaintext
project-average-calculator/
│
├── README.md
├── package.json
├── public/
│   └── index.html
├── src/
│   ├── components/
│   │   ├── AverageTable.jsx
│   │   ├── InputForm.jsx
│   │   └── FeatureList.jsx
│   ├── systems/
│   │   ├── calculation.js
│   │   └── validation.js
│   ├── features/
│   │   ├── addItem.js
│   │   ├── removeItem.js
│   │   ├── editItem.js
│   │   └── exportResult.js
│   ├── App.jsx
│   └── index.js
├── tests/
│   ├── calculation.test.js
│   └── validation.test.js
└── .gitignore

# ตัวอย่างโค้ดแต่ละไฟล์

src/systems/calculation.js
v1
export function calculateAverage(numbers) {
  if (!Array.isArray(numbers) || numbers.length === 0) return 0;
  const sum = numbers.reduce((acc, curr) => acc + curr, 0);
  return sum / numbers.length;
}


src/systems/validation.js
v1
export function isValidNumber(value) {
  return typeof value === "number" && !isNaN(value);
}


src/features/addItem.js
v1
export function addItem(list, item) {
  return [...list, item];
}


src/features/removeItem.js
v1
export function removeItem(list, index) {
  return list.filter((_, i) => i !== index);
}


src/components/AverageTable.jsx
v1
import React from "react";
export default function AverageTable({ numbers, average }) {
  return (
    <table>
      <thead>
        <tr>

src/components/InputForm.jsx
v1
import React, { useState } from "react";
export default function InputForm({ onAdd }) {
  const [value, setValue] = useState("");
  return (
    <form
      onSubmit={e => {

src/components/FeatureList.jsx
v1
import React from "react";
export default function FeatureList() {
  return (
    <ul>
      <li>เพิ่มข้อมูล</li>
      <li>ลบข้อมูล</li>
# ตัวอย่างไฟล์เพิ่มเติมหรือโค้ดเชื่อมโยงระหว่างฟีเจอร์ 

# ตัวอย่างไฟล์ทั้งหมดที่จำเป็นสำหรับโปรเจค “คำนวณค่าเฉลี่ย” (Average Calculator) ซึ่งรวมถึงระบบหลัก ฟีเจอร์
แน่นอนครับ! ต่อไปนี้คือตัวอย่างไฟล์ทั้งหมดที่จำเป็นสำหรับโปรเจค “คำนวณค่าเฉลี่ย” (Average Calculator) ซึ่งรวมถึงระบบหลัก ฟีเจอร์ และคอมโพเนนต์แสดงผลแบบ React:


package.json
{
  "name": "project-average-calculator",
  "version": "1.0.0",
  "description": "แอปคำนวณค่าเฉลี่ยตัวเลขด้วย React",
  "main": "src/index.js",
  "scripts": {

src/systems/calculation.js
v2
export function calculateAverage(numbers) {
  if (!Array.isArray(numbers) || numbers.length === 0) return 0;
  const sum = numbers.reduce((acc, curr) => acc + curr, 0);
  return sum / numbers.length;
}


src/systems/validation.js
v2
export function isValidNumber(value) {
  return typeof value === "number" && !isNaN(value);
}


src/features/addItem.js
v2
export function addItem(list, item) {
  return [...list, item];
}


src/features/removeItem.js
v2
export function removeItem(list, index) {
  return list.filter((_, i) => i !== index);
}


src/features/editItem.js
export function editItem(list, index, newValue) {
  return list.map((item, i) => (i === index ? newValue : item));
}


src/features/exportResult.js
// ส่งออกผลลัพธ์เป็นไฟล์ CSV
export function exportResult(numbers, average) {
  const header = "ลำดับ,ค่า\n";
  const rows = numbers.map((num, idx) => `${idx + 1},${num}`).join("\n");
  const avgRow = `ค่าเฉลี่ย,${average}`;
  const csv = header + rows + "\n" + avgRow;

src/components/AverageTable.jsx
v2
import React from "react";
export default function AverageTable({ numbers, average, onEdit, onRemove }) {
  return (
    <table>
      <thead>
        <tr>

src/components/InputForm.jsx
v2
import React, { useState } from "react";
export default function InputForm({ onAdd }) {
  const [value, setValue] = useState("");
  return (
    <form
      onSubmit={e => {

src/components/FeatureList.jsx
v2
import React from "react";
export default function FeatureList() {
  return (
    <ul>
      <li>เพิ่มข้อมูล</li>
      <li>ลบข้อมูล</li>

src/App.jsx
v1
import React, { useState } from "react";
import { calculateAverage } from "./systems/calculation";
import { addItem } from "./features/addItem";
import { removeItem } from "./features/removeItem";
import { editItem } from "./features/editItem";
import { exportResult } from "./features/exportResult";

src/index.js
v1
import React from "react";
import { createRoot } from "react-dom/client";
import App from "./App";

const container = document.getElementById("root");
const root = createRoot(container);

public/index.html
v1
<!DOCTYPE html>
<html lang="th">
  <head>
    <meta charset="UTF-8" />
    <title>เครื่องคำนวณค่าเฉลี่ย</title>
  </head>

README.md
v1
# เครื่องคำนวณค่าเฉลี่ย (Average Calculator)

## ฟีเจอร์หลัก
- เพิ่มข้อมูลตัวเลข
- ลบข้อมูลตัวเลข
- แก้ไขข้อมูลในรายการ

tests/calculation.test.js
import { calculateAverage } from "../src/systems/calculation";

test("ค่าเฉลี่ยของ [1,2,3,4,5] คือ 3", () => {
  expect(calculateAverage([1, 2, 3, 4, 5])).toBe(3);
});


tests/validation.test.js
import { isValidNumber } from "../src/systems/validation";

test("2 เป็นตัวเลขที่ถูกต้อง", () => {
  expect(isValidNumber(2)).toBe(true);
});


.gitignore
node_modules
build
dist
.env

# ไฟล์เพิ่มเติม เช่น การปรับแต่ง UI, รองรับภาษาอื่น หรือเชื่อมต่อ backend 

You said: ต้องการไฟล์เพิ่มเติม เช่น การปรับแต่ง UI, รองรับภาษาอื่น หรือเชื่อมต่อ backend
ต้องการไฟล์เพิ่มเติม เช่น การปรับแต่ง UI, รองรับภาษาอื่น หรือเชื่อมต่อ backend  และในส่วนอื่นๆทั้งหมด
Copilot said: ได้เลยครับ! ต่อไปนี้คือตัวอย่างไฟล์เพิ่มเติมสำหรับโปรเจค “คำนวณค่าเฉลี่ย” ที่ครอบคลุม **1. การปรับแต่ง
ได้เลยครับ! ต่อไปนี้คือตัวอย่างไฟล์เพิ่มเติมสำหรับโปรเจค “คำนวณค่าเฉลี่ย” ที่ครอบคลุม
1. การปรับแต่ง UI (CSS) 2. รองรับภาษาอื่น (i18n) 3. ตัวอย่างเชื่อมต่อ backend (API) 4. ส่วนอื่นๆ ที่ควรมีในโปรเจค React สมัยใหม่


src/styles/App.css
body {
  font-family: 'Sarabun', sans-serif;
  background: #f5f5f5;
  margin: 0;
  padding: 0;
}

src/i18n/th.js
export default {
  title: "เครื่องคำนวณค่าเฉลี่ย",
  average: "ค่าเฉลี่ย",
  add: "เพิ่ม",
  edit: "แก้ไข",
  remove: "ลบ",

src/i18n/en.js
export default {
  title: "Average Calculator",
  average: "Average",
  add: "Add",
  edit: "Edit",
  remove: "Remove",

src/i18n/index.js
v1
import th from "./th";
import en from "./en";
const langs = { th, en };
export default function getText(lang, key) {
  return langs[lang]?.[key] ?? langs["th"][key];
}

src/components/LanguageSelector.jsx
v1
import React from "react";
export default function LanguageSelector({ lang, setLang }) {
  return (
    <div style={{ marginBottom: "1em" }}>
      <button onClick={() => setLang("th")} disabled={lang === "th"}>
        ไทย

src/components/AverageTable.jsx
v3
import React from "react";
import getText from "../i18n";
export default function AverageTable({ numbers, average, onEdit, onRemove, lang }) {
  return (
    <table>
      <thead>

src/components/InputForm.jsx
v3
import React, { useState } from "react";
import getText from "../i18n";
export default function InputForm({ onAdd, lang }) {
  const [value, setValue] = useState("");
  return (
    <form

src/components/FeatureList.jsx
v3
import React from "react";
import { getFeatureList } from "../i18n";
export default function FeatureList({ lang }) {
  return (
    <ul>
      {getFeatureList(lang).map((txt, idx) => (

src/api/average.js
v1
// สมมุติ backend api ด้วย fetch
export async function fetchNumbers() {
  const res = await fetch("/api/numbers");
  return await res.json();
}
export async function postNumber(num) {

src/App.jsx
v2
import React, { useState, useEffect } from "react";
import { calculateAverage } from "./systems/calculation";
import { addItem } from "./features/addItem";
import { removeItem } from "./features/removeItem";
import { editItem } from "./features/editItem";
import { exportResult } from "./features/exportResult";

src/index.js
v2
import React from "react";
import { createRoot } from "react-dom/client";
import App from "./App";
const container = document.getElementById("root");
const root = createRoot(container);
root.render(<App />);

public/index.html
v2
<!DOCTYPE html>
<html lang="th">
  <head>
    <meta charset="UTF-8" />
    <title>เครื่องคำนวณค่าเฉลี่ย / Average Calculator</title>
    <link rel="stylesheet" href="%PUBLIC_URL%/src/styles/App.css" />
คุณสามารถเพิ่ม backend จริง (Node.js, Express, ฯลฯ) ได้ หรือ mock API ด้วยไฟล์ JSON/localStorage ก็ได้
ถ้าต้องการตัวอย่าง backend Node.js, Express เพิ่มเติม แจ้งได้ครับ!

# เพิ่มเติม:

UI สามารถปรับได้ตามไฟล์ CSS
ภาษา (i18n) สามารถเลือกไทย/อังกฤษ
API รองรับเชื่อมต่อ backend
อื่นๆ เช่น การทดสอบ, Lint, README, .gitignore มีตัวอย่างให้แล้วในข้อความก่อนหน้า
หากต้องการส่วนใดเฉพาะ หรือขยายในแต่ละจุด แจ้งรายละเอียดได้เลยครับ!

# ส่วนขยายเฉพาะ หรือขยายในแต่ละจุดหลัก ทั้งหมด
ต้องการส่วนขยายเฉพาะ หรือขยายในแต่ละจุดหลัก ทั้งหมด
Copilot said: แน่นอนครับ! ต่อไปนี้คือ “ส่วนขยาย” และ “รายละเอียดเพิ่มเติม” ในแต่ละจุดหลัก สำหรับโปรเจคคำนวณค่าเฉลี่ย
แน่นอนครับ! ต่อไปนี้คือ “ส่วนขยาย” และ “รายละเอียดเพิ่มเติม” ในแต่ละจุดหลัก สำหรับโปรเจคคำนวณค่าเฉลี่ย
ผมจะแยกแต่ละหัวข้อเป็นไฟล์ตัวอย่างที่ขยายจากโครงสร้างเบื้องต้น เพื่อให้คุณนำไปใช้งานหรือปรับแต่งได้อย่างครบถ้วน

1. ส่วนขยายการปรับแต่ง UI (เช่น Theme, Responsive, Animation)

src/styles/theme.css
:root {
  --primary: #2196f3;
  --secondary: #1769aa;
  --danger: #d32f2f;
  --success: #388e3c;
  --bg: #f5f5f5;
2. ส่วนขยายรองรับภาษา (เพิ่มภาษาใหม่, ตัวอย่างการเปลี่ยนภาษาอัตโนมัติ)

src/i18n/zh.js
export default {
  title: "平均值计算器",
  average: "平均值",
  add: "添加",
  edit: "编辑",
  remove: "删除",

src/i18n/index.js
v2
import th from "./th";
import en from "./en";
import zh from "./zh";
const langs = { th, en, zh };
export default function getText(lang, key) {
  return langs[lang]?.[key] ?? langs["th"][key];

src/components/LanguageSelector.jsx
v2
import React from "react";
import { supportedLangs } from "../i18n";
export default function LanguageSelector({ lang, setLang }) {
  return (
    <div style={{ marginBottom: "1em" }}>
      {supportedLangs.map(code => (
3. ส่วนขยายเชื่อมต่อ backend (Express + ตัวอย่าง API)

backend/server.js
const express = require('express');
const cors = require('cors');
const app = express();
app.use(cors());
app.use(express.json());


src/api/average.js
v2
export async function fetchNumbers() {
  const res = await fetch("http://localhost:8080/api/numbers");
  return await res.json();
}
export async function postNumber(num) {
  const res = await fetch("http://localhost:8080/api/numbers", {
4. ส่วนขยายฟีเจอร์/การใช้งาน (เช่น Import, Export, Undo/Redo, การแจ้งเตือน)

src/features/importNumbers.js
// Import ตัวเลขจากไฟล์ CSV
export function importNumbersFromCSV(file, callback) {
  const reader = new FileReader();
  reader.onload = function (e) {
    const text = e.target.result;
    const lines = text.split(/\r?\n/);

src/components/Notification.jsx
import React from "react";
export default function Notification({ message, type = "success", onClose }) {
  return (
    <div style={{
      background: type === "success" ? "#388e3c" : "#d32f2f",
      color: "#fff",
5. ส่วนขยาย Testing & Linting

.eslintrc.json
{
  "extends": ["react-app", "eslint:recommended"],
  "rules": {
    "semi": ["error", "always"],
    "quotes": ["error", "double"],
    "no-unused-vars": ["warn"]

tests/feature-import.test.js
import { importNumbersFromCSV } from "../src/features/importNumbers";
test("importNumbersFromCSV แปลงไฟล์ CSV เป็น array ตัวเลข", done => {
  const file = new Blob(["1\n2\n3\n4\n"], { type: "text/csv" });
  importNumbersFromCSV(file, nums => {
    expect(nums).toEqual([1,2,3,4]);
    done();
6. ส่วนขยาย README (ตัวอย่าง section เพิ่มเติม)

README.md
v2
## ส่วนขยาย / Extension

- รองรับธีม (Theme) และ Responsive
- เพิ่มภาษาใหม่ได้ง่าย (ดูไฟล์ใน src/i18n/)
- ใช้งานร่วมกับ backend (Express, API)
- ฟีเจอร์ Import/Export, Undo/Redo, การแจ้งเตือน
7. ส่วนขยายการใช้งาน Import/Export ใน App

src/App.jsx
v3
// เพิ่มฟีเจอร์ Import CSV และใช้ Notification
import React, { useState, useEffect } from "react";
import { calculateAverage } from "./systems/calculation";
import { addItem } from "./features/addItem";
import { removeItem } from "./features/removeItem";
import { editItem } from "./features/editItem";
หากต้องการขยายจุดใดเพิ่มเติม แจ้งได้ทันที
ส่วนที่นำเสนอคือ ตัวอย่างไฟล์สำหรับขยายความสามารถแต่ละจุดหลัก (UI, ภาษา, Backend, ฟีเจอร์, ทดสอบ, README และการใช้งานจริงใน App)
# ตัวอย่างโครงการเว็บแอปคำนวณค่าเฉลี่ย

project-average-calculator/
│
├── README.md                    # อธิบายโครงการและวิธีการใช้งาน
├── package.json                 # ข้อมูล dependencies (ถ้าใช้ Node.js)
├── public/                      # ไฟล์ static เช่น index.html, รูปภาพ
│   └── index.html
├── src/
│   ├── components/              # ส่วนประกอบ UI เช่น ตาราง, ฟอร์ม
│   │   ├── AverageTable.js      # ตารางแสดงผลค่าเฉลี่ย
│   │   ├── InputForm.js         # ฟอร์มกรอกข้อมูล
│   │   └── FeatureList.js       # แสดงรายการฟีเจอร์ทั้งหมด
│   ├── systems/                 # ระบบหลัก (business logic)
│   │   ├── calculation.js       # ฟังก์ชันคำนวณค่าเฉลี่ย
│   │   └── validation.js        # ฟังก์ชันตรวจสอบข้อมูล
│   ├── features/                # ฟีเจอร์ย่อย
│   │   ├── addItem.js           # เพิ่มข้อมูล
│   │   ├── removeItem.js        # ลบข้อมูล
│   │   ├── editItem.js          # แก้ไขข้อมูล
│   │   └── exportResult.js      # ส่งออกผลลัพธ์
│   ├── App.js                   # Root component
│   └── index.js                 # Entry point
├── tests/                       # Unit test
│   ├── calculation.test.js
│   └── validation.test.js
└── .gitignore

รายการระบบ (Systems)
ระบบคำนวณค่าเฉลี่ย (calculation.js): รับข้อมูลและคำนวณค่าเฉลี่ย
ระบบตรวจสอบข้อมูล (validation.js): ตรวจสอบ ความถูกต้องก่อนคำนวณ

รายการฟีเจอร์ (Features)
เพิ่มข้อมูล (addItem.js): เพิ่มข้อมูลใหม่เข้ารายการ
ลบข้อมูล (removeItem.js): ลบข้อมูลออกจากรายการ
แก้ไขข้อมูล (editItem.js): แก้ไขข้อมูลที่มีอยู่แล้ว
แสดงผลลัพธ์ (AverageTable.js): แสดงผลค่าเฉลี่ย
ส่งออกผลลัพธ์ (exportResult.js): ส่งออกผลลัพธ์เป็นไฟล์ (CSV, PDF ฯลฯ)

ตัวอย่างแสดงผล
หน้าเว็บมีฟอร์มให้กรอกข้อมูล
มีตารางแสดงข้อมูลและค่าเฉลี่ย
มีปุ่มเพิ่ม ลบ แก้ไข และส่งออกผลลัพธ์
# ตัวอย่างไฟล์ทั้งหมดที่จำเป็นสำหรับโปรเจค “คำนวณค่าเฉลี่ย” (Average Calculator) ซึ่งรวมถึงระบบหลัก ฟีเจอร์ และคอมโพเนนต์แสดงผลแบบ React:

{
  "name": "project-average-calculator",
  "version": "1.0.0",
  "description": "แอปคำนวณค่าเฉลี่ยตัวเลขด้วย React",
  "main": "src/index.js",
  "scripts": {
    "start": "react-scripts start",
    "test": "react-scripts test",
    "build": "react-scripts build"
  },
  "dependencies": {
    "react": "^18.0.0",
    "react-dom": "^18.0.0"
  }
}

export function calculateAverage(numbers) {
  if (!Array.isArray(numbers) || numbers.length === 0) return 0;
  const sum = numbers.reduce((acc, curr) => acc + curr, 0);
  return sum / numbers.length;
}

export function isValidNumber(value) {
  return typeof value === "number" && !isNaN(value);
}

export function addItem(list, item) {
  return [...list, item];
}

export function removeItem(list, index) {
  return list.filter((_, i) => i !== index);
}

export function editItem(list, index, newValue) {
  return list.map((item, i) => (i === index ? newValue : item));
}

// ส่งออกผลลัพธ์เป็นไฟล์ CSV
export function exportResult(numbers, average) {
  const header = "ลำดับ,ค่า\n";
  const rows = numbers.map((num, idx) => `${idx + 1},${num}`).join("\n");
  const avgRow = `ค่าเฉลี่ย,${average}`;
  const csv = header + rows + "\n" + avgRow;
  // สร้าง Blob สำหรับดาวน์โหลด
  const blob = new Blob([csv], { type: "text/csv" });
  const url = URL.createObjectURL(blob);
  return url;
}

import React from "react";
export default function AverageTable({ numbers, average, onEdit, onRemove }) {
  return (
    <table>
      <thead>
        <tr>
          <th>ลำดับ</th>
          <th>ค่า</th>
          <th>แก้ไข</th>
          <th>ลบ</th>
        </tr>
      </thead>
      <tbody>
        {numbers.map((num, idx) => (
          <tr key={idx}>
            <td>{idx + 1}</td>
            <td>{num}</td>
            <td>
              <button onClick={() => onEdit(idx)}>แก้ไข</button>
            </td>
            <td>
              <button onClick={() => onRemove(idx)}>ลบ</button>
            </td>
          </tr>
        ))}
        <tr>
          <td colSpan={2}>ค่าเฉลี่ย</td>
          <td colSpan={2}>{average}</td>
        </tr>
      </tbody>
    </table>
  );
}

import React, { useState } from "react";
export default function InputForm({ onAdd }) {
  const [value, setValue] = useState("");
  return (
    <form
      onSubmit={e => {
        e.preventDefault();
        if (!isNaN(Number(value)) && value !== "") {
          onAdd(Number(value));
          setValue("");
        }
      }}
    >
      <input
        type="number"
        value={value}
        onChange={e => setValue(e.target.value)}
        placeholder="กรอกตัวเลข"
      />
      <button type="submit">เพิ่ม</button>
    </form>
  );
}

import React from "react";
export default function FeatureList() {
  return (
    <ul>
      <li>เพิ่มข้อมูล</li>
      <li>ลบข้อมูล</li>
      <li>แก้ไขข้อมูล</li>
      <li>แสดงผลลัพธ์</li>
      <li>ส่งออกผลลัพธ์</li>
    </ul>
  );
}

import React, { useState } from "react";
import { calculateAverage } from "./systems/calculation";
import { addItem } from "./features/addItem";
import { removeItem } from "./features/removeItem";
import { editItem } from "./features/editItem";
import { exportResult } from "./features/exportResult";
import InputForm from "./components/InputForm";
import AverageTable from "./components/AverageTable";
import FeatureList from "./components/FeatureList";

export default function App() {
  const [numbers, setNumbers] = useState([]);
  const [editingIdx, setEditingIdx] = useState(null);
  const [editingValue, setEditingValue] = useState("");

  const average = calculateAverage(numbers);

  const handleAdd = num => setNumbers(addItem(numbers, num));
  const handleRemove = idx => setNumbers(removeItem(numbers, idx));
  const handleEdit = idx => {
    setEditingIdx(idx);
    setEditingValue(numbers[idx]);
  };
  const handleEditSubmit = () => {
    setNumbers(editItem(numbers, editingIdx, Number(editingValue)));
    setEditingIdx(null);
    setEditingValue("");
  };
  const handleExport = () => {
    const url = exportResult(numbers, average);
    const link = document.createElement("a");
    link.href = url;
    link.download = "average.csv";
    link.click();
  };

  return (
    <div>
      <h1>เครื่องคำนวณค่าเฉลี่ย</h1>
      <FeatureList />
      <InputForm onAdd={handleAdd} />
      {editingIdx !== null && (
        <div>
          <input
            type="number"
            value={editingValue}
            onChange={e => setEditingValue(e.target.value)}
          />
          <button onClick={handleEditSubmit}>บันทึก</button>
          <button onClick={() => setEditingIdx(null)}>ยกเลิก</button>
        </div>
      )}
      <AverageTable
        numbers={numbers}
        average={average}
        onEdit={handleEdit}
        onRemove={handleRemove}
      />
      <button onClick={handleExport}>ส่งออกผลลัพธ์</button>
    </div>
  );
}

import React from "react";
import { createRoot } from "react-dom/client";
import App from "./App";

const container = document.getElementById("root");
const root = createRoot(container);
root.render(<App />);

<!DOCTYPE html>
<html lang="th">
  <head>
    <meta charset="UTF-8" />
    <title>เครื่องคำนวณค่าเฉลี่ย</title>
  </head>
  <body>
    <div id="root"></div>
  </body>
</html>

# เครื่องคำนวณค่าเฉลี่ย (Average Calculator)

## ฟีเจอร์หลัก
- เพิ่มข้อมูลตัวเลข
- ลบข้อมูลตัวเลข
- แก้ไขข้อมูลในรายการ
- คำนวณและแสดงผลค่าเฉลี่ย
- ส่งออกผลลัพธ์เป็นไฟล์ CSV

## วิธีการใช้งาน
1. ติดตั้ง dependencies ด้วย `npm install`
2. รันโปรเจคด้วย `npm start`
3. เปิดเบราว์เซอร์ที่ http://localhost:3000

## โครงสร้างโปรเจค

- `src/systems/` ฟังก์ชันระบบหลัก
- `src/features/` ฟีเจอร์ย่อย
- `src/components/` ส่วนประกอบ UI

## ตัวอย่างผลลัพธ์

- ฟอร์มกรอกตัวเลข
- ตารางแสดงข้อมูล และค่าเฉลี่ย
- ปุ่มสำหรับเพิ่ม, ลบ, แก้ไข, ส่งออก

import { calculateAverage } from "../src/systems/calculation";

test("ค่าเฉลี่ยของ [1,2,3,4,5] คือ 3", () => {
  expect(calculateAverage([1, 2, 3, 4, 5])).toBe(3);
});

test("ถ้าอาร์เรย์ว่าง, ค่าเฉลี่ยเท่ากับ 0", () => {
  expect(calculateAverage([])).toBe(0);
});

import { isValidNumber } from "../src/systems/validation";

test("2 เป็นตัวเลขที่ถูกต้อง", () => {
  expect(isValidNumber(2)).toBe(true);
});

test("'a' ไม่เป็นตัวเลขที่ถูกต้อง", () => {
  expect(isValidNumber("a")).toBe(false);
});

node_modules
build
dist
.env
# ตัวอย่างไฟล์เพิ่มเติมสำหรับโปรเจค “คำนวณค่าเฉลี่ย” ที่ครอบคลุม
1. การปรับแต่ง UI (CSS) 2. รองรับภาษาอื่น (i18n) 3. ตัวอย่างเชื่อมต่อ backend (API) 4. ส่วนอื่นๆ ที่ควรมีในโปรเจค React สมัยใหม่

body {
  font-family: 'Sarabun', sans-serif;
  background: #f5f5f5;
  margin: 0;
  padding: 0;
}
.app-container {
  max-width: 640px;
  margin: 2em auto;
  padding: 2em;
  background: #fff;
  border-radius: 14px;
  box-shadow: 0 2px 8px #9992;
}
h1 {
  color: #2d3e50;
}
button {
  background: #2196f3;
  color: white;
  border: none;
  border-radius: 6px;
  padding: 0.5em 1em;
  cursor: pointer;
  margin: 0 4px;
}
button:hover {
  background: #1769aa;
}
input[type="number"] {
  padding: 0.4em;
  border: 1px solid #ccc;
  border-radius: 6px;
}
table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 1em;
}
th, td {
  border: 1px solid #ddd;
  padding: 0.6em;
  text-align: center;
}
tr:nth-child(even) {
  background: #f8f8f8;
}

export default {
  title: "เครื่องคำนวณค่าเฉลี่ย",
  average: "ค่าเฉลี่ย",
  add: "เพิ่ม",
  edit: "แก้ไข",
  remove: "ลบ",
  save: "บันทึก",
  cancel: "ยกเลิก",
  inputPlaceholder: "กรอกตัวเลข",
  export: "ส่งออกผลลัพธ์",
  featureList: [
    "เพิ่มข้อมูล",
    "ลบข้อมูล",
    "แก้ไขข้อมูล",
    "แสดงผลลัพธ์",
    "ส่งออกผลลัพธ์"
  ]
};

export default {
  title: "Average Calculator",
  average: "Average",
  add: "Add",
  edit: "Edit",
  remove: "Remove",
  save: "Save",
  cancel: "Cancel",
  inputPlaceholder: "Enter a number",
  export: "Export Result",
  featureList: [
    "Add item",
    "Remove item",
    "Edit item",
    "Show result",
    "Export result"
  ]
};

export default {
  title: "Average Calculator",
  average: "Average",
  add: "Add",
  edit: "Edit",
  remove: "Remove",
  save: "Save",
  cancel: "Cancel",
  inputPlaceholder: "Enter a number",
  export: "Export Result",
  featureList: [
    "Add item",
    "Remove item",
    "Edit item",
    "Show result",
    "Export result"
  ]
};

import th from "./th";
import en from "./en";
const langs = { th, en };
export default function getText(lang, key) {
  return langs[lang]?.[key] ?? langs["th"][key];
}
export const getFeatureList = lang => langs[lang]?.featureList ?? langs["th"].featureList;

import React from "react";
export default function LanguageSelector({ lang, setLang }) {
  return (
    <div style={{ marginBottom: "1em" }}>
      <button onClick={() => setLang("th")} disabled={lang === "th"}>
        ไทย
      </button>
      <button onClick={() => setLang("en")} disabled={lang === "en"}>
        EN
      </button>
    </div>
  );
}

import React from "react";
import getText from "../i18n";
export default function AverageTable({ numbers, average, onEdit, onRemove, lang }) {
  return (
    <table>
      <thead>
        <tr>
          <th>ลำดับ</th>
          <th>{getText(lang, "average")}</th>
          <th>{getText(lang, "edit")}</th>
          <th>{getText(lang, "remove")}</th>
        </tr>
      </thead>
      <tbody>
        {numbers.map((num, idx) => (
          <tr key={idx}>
            <td>{idx + 1}</td>
            <td>{num}</td>
            <td>
              <button onClick={() => onEdit(idx)}>{getText(lang, "edit")}</button>
            </td>
            <td>
              <button onClick={() => onRemove(idx)}>{getText(lang, "remove")}</button>
            </td>
          </tr>
        ))}
        <tr>
          <td colSpan={2}>{getText(lang, "average")}</td>
          <td colSpan={2}>{average}</td>
        </tr>
      </tbody>
    </table>
  );
}

import React from "react";
import getText from "../i18n";
export default function AverageTable({ numbers, average, onEdit, onRemove, lang }) {
  return (
    <table>
      <thead>
        <tr>
          <th>ลำดับ</th>
          <th>{getText(lang, "average")}</th>
          <th>{getText(lang, "edit")}</th>
          <th>{getText(lang, "remove")}</th>
        </tr>
      </thead>
      <tbody>
        {numbers.map((num, idx) => (
          <tr key={idx}>
            <td>{idx + 1}</td>
            <td>{num}</td>
            <td>
              <button onClick={() => onEdit(idx)}>{getText(lang, "edit")}</button>
            </td>
            <td>
              <button onClick={() => onRemove(idx)}>{getText(lang, "remove")}</button>
            </td>
          </tr>
        ))}
        <tr>
          <td colSpan={2}>{getText(lang, "average")}</td>
          <td colSpan={2}>{average}</td>
        </tr>
      </tbody>
    </table>
  );
}

import React, { useState } from "react";
import getText from "../i18n";
export default function InputForm({ onAdd, lang }) {
  const [value, setValue] = useState("");
  return (
    <form
      onSubmit={e => {
        e.preventDefault();
        if (!isNaN(Number(value)) && value !== "") {
          onAdd(Number(value));
          setValue("");
        }
      }}
    >
      <input
        type="number"
        value={value}
        onChange={e => setValue(e.target.value)}
        placeholder={getText(lang, "inputPlaceholder")}
      />
      <button type="submit">{getText(lang, "add")}</button>
    </form>
  );
}

import React from "react";
import { getFeatureList } from "../i18n";
export default function FeatureList({ lang }) {
  return (
    <ul>
      {getFeatureList(lang).map((txt, idx) => (
        <li key={idx}>{txt}</li>
      ))}
    </ul>
  );
}

// สมมุติ backend api ด้วย fetch
export async function fetchNumbers() {
  const res = await fetch("/api/numbers");
  return await res.json();
}
export async function postNumber(num) {
  const res = await fetch("/api/numbers", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ value: num })
  });
  return await res.json();
}
// API อื่นๆ เช่น PUT, DELETE, PATCH ก็ทำคล้ายกัน

import React, { useState, useEffect } from "react";
import { calculateAverage } from "./systems/calculation";
import { addItem } from "./features/addItem";
import { removeItem } from "./features/removeItem";
import { editItem } from "./features/editItem";
import { exportResult } from "./features/exportResult";
import InputForm from "./components/InputForm";
import AverageTable from "./components/AverageTable";
import FeatureList from "./components/FeatureList";
import LanguageSelector from "./components/LanguageSelector";
import getText from "./i18n";
import "./styles/App.css";
import { fetchNumbers, postNumber } from "./api/average";

export default function App() {
  const [numbers, setNumbers] = useState([]);
  const [editingIdx, setEditingIdx] = useState(null);
  const [editingValue, setEditingValue] = useState("");
  const [lang, setLang] = useState("th");

  useEffect(() => {
    // ตัวอย่างการโหลดข้อมูลจาก backend
    fetchNumbers().then(data => setNumbers(data.numbers ?? []));
  }, []);

  const average = calculateAverage(numbers);

  const handleAdd = async num => {
    const res = await postNumber(num);
    setNumbers(res.numbers);
  };
  const handleRemove = idx => setNumbers(removeItem(numbers, idx));
  const handleEdit = idx => {
    setEditingIdx(idx);
    setEditingValue(numbers[idx]);
  };
  const handleEditSubmit = () => {
    setNumbers(editItem(numbers, editingIdx, Number(editingValue)));
    setEditingIdx(null);
    setEditingValue("");
  };
  const handleExport = () => {
    const url = exportResult(numbers, average);
    const link = document.createElement("a");
    link.href = url;
    link.download = "average.csv";
    link.click();
  };

  return (
    <div className="app-container">
      <LanguageSelector lang={lang} setLang={setLang} />
      <h1>{getText(lang, "title")}</h1>
      <FeatureList lang={lang} />
      <InputForm onAdd={handleAdd} lang={lang} />
      {editingIdx !== null && (
        <div>
          <input
            type="number"
            value={editingValue}
            onChange={e => setEditingValue(e.target.value)}
          />
          <button onClick={handleEditSubmit}>{getText(lang, "save")}</button>
          <button onClick={() => setEditingIdx(null)}>{getText(lang, "cancel")}</button>
        </div>
      )}
      <AverageTable
        numbers={numbers}
        average={average}
        onEdit={handleEdit}
        onRemove={handleRemove}
        lang={lang}
      />
      <button onClick={handleExport}>{getText(lang, "export")}</button>
    </div>
  );
}

import React from "react";
import { createRoot } from "react-dom/client";
import App from "./App";
const container = document.getElementById("root");
const root = createRoot(container);
root.render(<App />);

<!DOCTYPE html>
<html lang="th">
  <head>
    <meta charset="UTF-8" />
    <title>เครื่องคำนวณค่าเฉลี่ย / Average Calculator</title>
    <link rel="stylesheet" href="%PUBLIC_URL%/src/styles/App.css" />
    <link href="https://fonts.googleapis.com/css?family=Sarabun:400,700&display=swap" rel="stylesheet">
  </head>
  <body>
    <div id="root"></div>
  </body>
</html>
# โปรเจคสำหรับ “คำนวณค่าเฉลี่ย” พร้อมระบบและฟีเจอร์ (Node.js + React)

# project-average-calculator/
│
├── README.md
├── package.json
├── public/
│   └── index.html
├── src/
│   ├── components/
│   │   ├── AverageTable.jsx
│   │   ├── InputForm.jsx
│   │   └── FeatureList.jsx
│   ├── systems/
│   │   ├── calculation.js
│   │   └── validation.js
│   ├── features/
│   │   ├── addItem.js
│   │   ├── removeItem.js
│   │   ├── editItem.js
│   │   └── exportResult.js
│   ├── App.jsx
│   └── index.js
├── tests/
│   ├── calculation.test.js
│   └── validation.test.js
└── .gitignore

# code 
export function calculateAverage(numbers) {
  if (!Array.isArray(numbers) || numbers.length === 0) return 0;
  const sum = numbers.reduce((acc, curr) => acc + curr, 0);
  return sum / numbers.length;
}

export function isValidNumber(value) {
  return typeof value === "number" && !isNaN(value);
}

export function addItem(list, item) {
  return [...list, item];
}

export function removeItem(list, index) {
  return list.filter((_, i) => i !== index);
}

import React from "react";
export default function AverageTable({ numbers, average }) {
  return (
    <table>
      <thead>
        <tr>
          <th>ลำดับ</th>
          <th>ค่า</th>
        </tr>
      </thead>
      <tbody>
        {numbers.map((num, idx) => (
          <tr key={idx}>
            <td>{idx + 1}</td>
            <td>{num}</td>
          </tr>
        ))}
        <tr>
          <td>ค่าเฉลี่ย</td>
          <td>{average}</td>
        </tr>
      </tbody>
    </table>
  );
}

import React, { useState } from "react";
export default function InputForm({ onAdd }) {
  const [value, setValue] = useState("");
  return (
    <form
      onSubmit={e => {
        e.preventDefault();
        if (!isNaN(Number(value))) {
          onAdd(Number(value));
          setValue("");
        }
      }}
    >
      <input
        type="number"
        value={value}
        onChange={e => setValue(e.target.value)}
        placeholder="กรอกตัวเลข"
      />
      <button type="submit">เพิ่ม</button>
    </form>
  );
}

import React from "react";
export default function FeatureList() {
  return (
    <ul>
      <li>เพิ่มข้อมูล</li>
      <li>ลบข้อมูล</li>
      <li>แก้ไขข้อมูล</li>
      <li>แสดงผลลัพธ์</li>
      <li>ส่งออกผลลัพธ์</li>
    </ul>
  );
}

