# AN-OPTIMISED-END-TO-END-SYSTEM-TO-IDENTIFY-HIGH-RISK-RUGBY-TACKLES

## Overview

Head injury in contact-based sports is a large problem for players. Due to the high volume
of continuous contact rugby has, making sure players are kept safe is vital. The Head Injury
Assessment (HIA) protocol is the main way rugby keeps its players safe. However, whether
a player is taken for a HIA is subject to bias by officials at every rugby match. Therefore,
this paper aims to create a consistent and accurate system to detect high-risk rugby tackles
that require a HIA. The system will consist of three models; player detection, tackle
detection and tackle risk classification. The models will be combined to
create an end-to-end system that can be used by rugby officials to make a safer game.

## Getting Started

The code is designed to run in a Google Colab enivronment. 

To get started running the system, open the notebook and ensure that you have a paid Google Colab account to access more powerful GPUs. The dependencies are included in the code cells of the system. 

Upload all videos of rugby tackles, Tackle.csv and coordinates.json to the content folder inside Google Colab. (The folder containing both the tackle videos and ground truth data 'Tackle.csv' can be accessed through this link https://drive.google.com/drive/folders/15YJ1UVApgQiuaSO7fiO_IpIZVbptqaQ5?usp=share_link).

## Usage

Begin by running OpenPose, you will need to change the following code with the name of each video. The path after "--video" will need to be changed to the path to the video you want to run OpenPose on. Also the name output mp4 on the last line will need to be changed so that you can distinguish the output files from one another.

!rm openpose.avi

!cd openpose && ./build/examples/openpose/openpose.bin --video /content/T87.mp4 --write_json ./output/ --display 0  --write_video ../openpose.avi --part_candidates True

#convert the result into MP4

!ffmpeg -y -loglevel info -i openpose.avi outputT87.mp4  ##Change for specifc video

Run all the code cells in order to run the system.

## Example

![T1frame2](https://user-images.githubusercontent.com/73236187/234690028-4ac97b58-a3b6-46bb-af48-bdabc3107161.png)

## Future Work

A recommendation for the future of this research is to continue to use
different methods to identify where the ball is. Using technologies like the Sportable ‘smart ball’ with accurate tracking of the ball using a GPS inside the ball could be used to bridge the gap for ball detection. This is subject to the data being available publicly, as of the time of writing this paper it is not.

The use of this system to improve player safety in rugby could have several potential benefits
for the sport. For one, it could reduce the risk of head injuries and other serious injuries that
can occur during play, which could in turn lead to a reduction in the number of missed games
or career-ending injuries. Additionally, by creating a safer playing environment, the sport could
potentially attract a wider range of players, including those who may have previously been hesitant
to participate due to safety concerns.

Furthermore, this research could inform the development of similar systems for other sports or
activities facing similar safety concerns. For example, contact sports such as American football
or hockey could potentially benefit from a similar system that identifies dangerous tackles or
hits. Other activities such as gymnastics or snowboarding could benefit from the use of similar
technology to monitor the safety of athletes during competitions. By developing and implementing
such systems, these sports could potentially become safer and more appealing to participants and
spectators alike.

Overall, this paper was able to accurately identify the risk of tackles in rugby game footage and
in particular highlight high-risk tackles that could be dangerous to the health of rugby players.
Using OpenPose and a series of checks to identify and classify the risk of tackles, this system could
potentially be employed in live game footage for the professional game to use to make referees’
decisions quicker and safer.

## Author

Adam Gilbert

Ag815@exeter.ac.uk

