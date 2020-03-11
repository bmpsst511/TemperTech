---
title: '機器手臂開發過程 Robot Arm Developing'
disqus: hackmd
---
# TemperTech
**J.T LEE**\
致力於發展具有人性的科技，輔助智慧科技,物聯網科技,虛擬實境等相關技術\
**同步於GITHUB 有溫度科技 TemperTech\
https://github.com/bmpsst511/TemperTech**

![](https://i.imgur.com/z9BOXR9.png)


機器手臂開發過程 Robot Arm Developing
===
![downloads](https://img.shields.io/github/downloads/atom/atom/total.svg)
![build](https://img.shields.io/appveyor/ci/:user/:repo.svg)
![chat](https://img.shields.io/discord/:serverId.svg)

[TOC]

## Beginners Guide

If you are a total beginner to this, start here!

1. 理解自由度
2. Visit Solidworks Tutorials
3. Visit Arduino Tutorials
4. Visit Electronic components Websites ex:Taobao(cn), Ruten/Shopee/UCI(TW), Amazon/SwitchScience(JP)
5. Start writing note!(not yet)

自由度Degree of Freedom
---
定義:描述一質點或剛體之運動位置所需之座標個數，或假設運動對中之一機件固定，而另一機件相對於此機件之位置所需要的獨立參數數目，亦可稱為可動度。(金謀療)

自由度是機器人學當中的一個重要技術概念，它是由機器人的各式結合決定，並直接影響到機器人的平面/空間機動性。對於自由度的概念，機械專業的學生可能是如數家珍，但對於大多數外行人像是小編我卻是霧裡看花摸不著頭腦，小編雖是機械專業但由於大學不學無術，對自由度一知半解，因此小編為大家講一講機器人的自由度，順便裡順自己的理解，若有講得不對或遺漏的地方，還請各位學術大神多多指教。


Degree of freedom is an important technical concept in robotics. It is determined by various combinations of robots and directly affects the plane / space mobility of the robot. Regarding the concept of degrees of freedom, mechanical students may be like a few treasures, but for most laymen like small editors, I am confused and confused. Although Xiaobian is a mechanical major, but because the university is not learned, The degree of freedom is only a half-knowledge, so I will tell you about the degree of freedom of robots, and by the way, your understanding. If there is something wrong or omitted, please give us a lot of academic advice.

![](https://i.imgur.com/SbFSnTe.png)

從圖片可以看出在一個坐標系中，可以允許沿著三個軸的平移與繞著三個軸的旋轉
**即總共有六個自由度**
It can be seen from the picture that in a coordinate system, translation along three axes and rotation around three axes can be allowed.
**There are six degrees of freedom in total.**

機構傳遞運動方式(乾擔帶過)
---
在小編本次機器手臂開發過程當中預計採用的為搖桿與旋轉
In the development of this robotic arm, we expect to use Mechanism rocker and rotation pairs.
![](https://i.imgur.com/c6vCPLr.png)**搖桿**
![](https://i.imgur.com/dmH2UwG.png)**旋轉**

自由度計算(青菜勝勝)
---
公式
$\sum_{i=0}^N\int_{a}^{b}g(t,i)\text{d}t$
DOF = 3(N-1)-2f_{L}-f_{H}\
DOF = 3(4-1)-2*2-0 = 3

其中 $N$ 代表機件數，$f_{L}$ 代表低對，$f_{H}$ 代表高對，迴轉對屬低對. 

**因此我們得到所設計的機械手臂自由度為3**

機器人的自由度是指機器人所具有的獨立坐標軸運動的數目，但一般不包括手部（末端操作器）的開合自由度。

Among them, $N$ represents the number of parts, $f_{L}$ represents the low pair, $f_ {H}$ represents the high pair, and the rotation pair is the low pair.

**So we get the designed robot arm with 3 degrees of freedom.**

The degree of freedom of the robot refers to the number of independent coordinate axis movements of the robot, but generally does not include the opening and closing degrees of freedom of the hand (end manipulator).

原文網址：https://kknews.cc/tech/jk6kel.html
![](https://i.imgur.com/xaZHb2u.png)

# 在繪製時如何知道實作出來後能用?
小編使用的繪圖軟體為Solidworks工程繪圖軟體來繪出自由度為三的機械手臂。在繪圖時，我們要盡量讓模型檔能被實際列印出來。因此諸如會使用到的伺服馬達與周邊配件都可以到"Grabcad" 下載 (Link:https://grabcad.com/library) ，下載後的第一件事，於繪圖軟體中確認模型尺寸是否正確，無誤之後開始基於配件的尺寸大小繪製其餘連桿與機件。成品如下圖：\
The drawing software used by Xiaobian is Solidworks engineering drawing software to draw a robot with three degrees of freedom. When drawing, we should try our best to make the model file actually print out. Therefore, such as the servo motor and peripheral accessories that can be used can be downloaded from "Grabcad" (Link: https: //grabcad.com/library). The first thing after downloading is to confirm the model size in the drawing software After that, we started to draw the remaining links and parts based on the size of the accessories. The finished product is as follows:
![](https://i.imgur.com/lt62ekb.png)


I am using the Solidworks to draw the robot arm midule

###### tags: `Robot Arm` `Interaction`

