## **Pattern 1: Renderer to main (one-way)**

ipcRenderer.send ⇒ ipcMain.on

## **Pattern 2: Renderer to main (two-way)**

렌더러가 메인을 호출하고, 호출 결과를 받아오는 경우(예: 파일 업로드시 파일명 받아오기)

ipcRenderer.invoke ⇔ ipcMain.handle

## **Pattern 3: Main to renderer**

webContents를 이용한다

## **Pattern 4: Renderer to renderer**