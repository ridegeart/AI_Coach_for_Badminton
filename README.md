# AI_Coach_for_Badminton
An implement of AI CUP 2023 [教電腦看羽球 - 台灣第一個結合AI與運動的競賽].

## Badminton Track Detect
- Code From [TrackNetV2: Efficient TrackNet (GitLab)]
- 使用 TrackNet.ipynb
- 輸入影片，輸出每幀球的畫素點座標。

## Court Detect
- 使用court_detect.ipynb
- 輸入圖像，輸出場地的中線與前/後場的座標。

## Pose Detect
- 使用 OpenPose.ipynb
- 輸入影像，輸出每幀裡每個人的關節處座標。(25個編碼)

## Object
- VideoName
- ShotSeq / HitFrame：Track Detect；只取軌跡內梯度變化最大(擊球點)的那幾幀。
- Hitter / Winner：Track Detect+Court Detect；判斷出第一打擊者屬於哪一半場，後幾拍直接生成。
- BallHeight / LandingX / LandingY：Track Detect，座標投映在場地上。
- RoundHead / BackHand：Pose Detect；讀取手部與頭部的高度進行判斷。
- HitterLocationX / HitterLocationY / DefenderLocationX / DefenderLocationY：Pose Detect；讀取腳部的座標。
- BallType：Track Detect+Pose Detect；讀取打者當下的姿態與球座標。
[教電腦看羽球 - 台灣第一個結合AI與運動的競賽]:https://aidea-web.tw/topic/cbea66cc-a993-4be8-933d-1aa9779001f8
[TrackNetV2: Efficient TrackNet (GitLab)]:https://nol.cs.nctu.edu.tw:234/open-source/TrackNetv2
