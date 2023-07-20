# ![](https://drive.google.com/uc?id=10INx5_pkhMcYRdx_OO4rXNXxcsvPtBYq) 如何在GitHub上添加貪吃蛇的動畫？

```diff
- 目前已經更新到3.0版，所以之前舊版的main.yml需要更新.
```

---

<!--ts-->
## 目錄
* [Step1. 開啟Repository，點選上方Actions頁籤](#step1)
* [Step2. 設置Workflow](#step2)
* [Step3. 建立main.yml檔案](#step3)
* [Step4. 刪掉main.yml的內容並且將以下代碼貼上](#step4)
* [Step5. 點擊在Actinos頁籤畫面左側的Generate Datas，並且點選右側的Run workflw.](#step5)
* [Step6. 檢查建置出來的.SVG檔案是否有出現在OutPut的分支上](#step6)
* [Step7. 添加以下的語法至README.md檔案上](#step7)
* [Step8. 跑吧，可愛的小蛇！](#step8)
* [參考資料](#參考資料)
<!--te-->

---

## Step1
### 開啟Repository，點選上方Actions頁籤
![](https://drive.google.com/uc?id=17746pbaUjQDEPkZDWPQRQ-xwVKb0d80n)

---

## Step2
### 設置Workflow
![](https://drive.google.com/uc?id=1xHVMHJCOvFU4MnYaveat4O_59E2MvOf3)

---

## Step3
### 建立main.yml檔案
![](https://drive.google.com/uc?id=1DqTFxjWwMdYyq0E6l2NZEL8CCvMenqDv)

---

## Step4
### 刪掉main.yml的內容並且將以下代碼貼上
```yml
name: Generate Datas

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"
  workflow_dispatch:

jobs:
  build:
    name: Jobs to update datas
    runs-on: ubuntu-latest
    steps:
      # Snake Animation
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: {{your_username}}
          svg_out_path: dist/github-contribution-grid-snake.svg

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
> ##### 將文中的 {{your_username}} 更換成你的GitHub username 並且上傳.

---


## Step5
### 點擊在Actinos頁籤畫面左側的Generate Datas，並且點選右側的Run workflw.
![](https://drive.google.com/uc?id=139WSa9l11SjQw6cnJ22dZgaQWI4eHzLm)

---

### 如果成功的話，則會顯示Workflow開始運行.
![](https://drive.google.com/uc?id=1ucmC8GHYyza-TPRvUu4nzs7gPZ-q0_WG)

---

> ### 如果運行失敗的話，則檢查在Setting/Actions/General/Workflow permissions/Read and write permissions 是否有被勾選.
> ![](https://drive.google.com/uc?id=10rt8_b40bPxjggCLWemt1qJ0VHGKKVOl)
> ![](https://drive.google.com/uc?id=1R5vdo5TRVIyLiWy0B9pyXDydAZ30rMrn)

---

## Step6
### 檢查建置出來的.SVG檔案是否有出現在OutPut的分支上
![](https://drive.google.com/uc?id=1_7pwN9DJn_SjWLEGSmGIiuZghDdjO7LV)

---

## Step7
### 添加以下的語法至README.md檔案上

```md
![Snake animation](https://github.com/{{your_username}}/{{your_username}}/blob/output/github-contribution-grid-snake.svg)
```
> ##### 將文中的 {{your_username}} 更換成你的GitHub username.

---

## Step8
### 跑吧，可愛的小蛇！
![Snake animation](https://github.com/RC-Dev-Tech/RC-Dev-Tech/blob/output/github-contribution-grid-snake.svg)

---

## 參考資料
* [generate-snake-game-from-github-contribution-grid](https://github.com/marketplace/actions/generate-snake-game-from-github-contribution-grid)
* [add-github-dark-snake-animation-readme](https://blog.arnabghosh.me/add-github-dark-snake-animation-readme#heading-2-go-to-action)  
* [github-contributions](https://github.com/topics/github-contributions)

---

<!--ts-->
#### [目錄 ↩](#目錄)
<!--te-->

---
