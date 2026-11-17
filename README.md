1.螢幕截圖
2.GitHub連結
https://github.com/hsuanlee03/1151VR-HW5-414262569-chlee
3.YouTube連結
https://youtu.be/d42VCFOQ5bM
4.說明製作流程和相關操作
<GitHub>
 1.開啟新的repository並命名
 2.在Settings中設定共享
 3.將專案儲存進去
<專案開啟>
 1.開啟Unity
 2.建立3D專案
< Terrain >
 1.在Hierarchy新增3D project的Terrain
 2.調整Terrain的座標，改成(-256，0，-256)
 3.選擇Terrain裡的【Raise or Lower Terrain】，在畫面的Z+方向拉地形
 4.在Unity Asset Store下載筆刷，並匯入專案裡
 5.在Terrain的Inspector找到下拉清單，改成Paint Texture，並新增Layer，選擇草地的texture
 6.再新增岩石紋理的筆刷，在山峰上點綴
 7.選擇Terrain裡的【Paint Trees】，點選Edit Trees新增樹的模型
 8.在畫面中畫出樹的範圍
<Main Camera>
 1.調整相機位置(調整至玩家後方)
 2.將相機旋轉方向向下調整，變成俯視的視角
<Pokemon>
 1.將下載好的Pokemon模型拉入Project，再拉入畫面中
 2. 加入Box Collider，並勾選 【Is Trigger】（方便偵測精靈球碰觸）
<玩家>
 1. 將下載好的玩家模型拉入Project，再拉入畫面中
 2.在Project新增Animator Controller，並命名為TrainerAnimator
 3. 點選Hierarchy中的訓練家角色，在Inspector點擊【Add Component】，搜尋並加入【Animator】
 4. 將剛剛建立的TrainerAnimator 拖曳到Animator組件的Controller欄位中。
 5. 點擊上方選單Window > Animation > Animation
 6. 在跳出的Animation視窗中央點擊Create，將動畫檔案命名為 ThrowArm.anim 並儲存
 7. 點擊 Animation 視窗左上角的紅色圓點按鈕（Record），錄製玩家的手臂揮動動作
 8.點擊TrainerAnimator開啟Animator視窗
 9.在空白處按右鍵Create State > Empty，將這個新方塊改名為 Idle
 10.在Idle上按右鍵選擇Set as Layer Default State
 11.切換到Animator左上角的Parameters分頁，點擊 + 號選擇【Trigger】，命名為ThrowTrigger
 12.在Idle上按右鍵選【Make Transition】，拉一條箭頭連到ThrowArm。點選這條箭頭，在右側Inspector取消勾選【Has Exit Time】，並在下方的 Conditions點 + 號加入【ThrowTrigger】
 13.從ThrowArm按右鍵選【Make Transition】拉一條箭頭連回 Idle（這條線保持勾選Has Exit Time）
 14.在Project視窗點選ThrowArm.anim，在右側Inspector取消勾選【Loop Time】
<精靈球>
 1.將下載好的精靈球模型拉入Project，再拉入畫面中
 2.將精靈球拉到玩家的手掌上(像是玩家握住精靈球)
<腳本>
 1.在Project新增MonoBehavior Script，並命名為PlayerThrow
 2.寫腳本
 3.點選character，把 PlayerThrow 腳本拖曳進去
 4.在Inspector找到PlayerThrow組件，依序將對應的物件拖進空格
<特效>
 1.在左上角Hierarchy新增【Particle System】，並將它改名為 CaptureEffect
 2.將CaptureEffect的位置調整到和Pokemon一樣的位置
 3.調整收服Pokemon時粒子特效爆發的參數
 4.更新腳本，新增當精靈球觸碰Pokemon時會觸發粒子特效
5.困境
	玩家手臂有成功揮動但精靈球沒有拋出去
PlayerThrow組件的所有欄位都要從Hierarchy中拉選，否則下方會有黃字警示，精靈球就無法順利拋出
