# mariadbDemoFront 前端

## 
本專案為 **MariaDB Demo** 的前端部分，使用 **Vue 3 + TypeScript** 開發，並透過 **Element Plus** 提供的 `el-table` 來顯示 **MariaDB** 中 `Reservations` 資料表的內容。

## 環境需求
- **Node.js** 
- **Vue 3**
- **Vite** 
- **Element Plus**
- 
- ## 選用技術
- **Vue 3**
- **TypeScript** 
- **Vite** 
- **Element Plus** 
- **Axios** 


## 安裝套件
### 1. 安裝依賴
```sh
npm install
```

### 2. 設定環境變數
 API 
```sh
const prefix = "http://localhost:2083/"
export const enum apis{
    test = `${prefix}Reservations/test`
}
```

### 3. 啟動伺服器
展示頁面面
```sh
npm run dev
```


## 建置
###  建置專案
```sh
npm run build
```


