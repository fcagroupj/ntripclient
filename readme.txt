		README.txt
	ROS node to feed RTK data to NovAtel model
	CASTER account: ste01565018:801655@mi.smartnetna.com:9950
	Hardware connection with NovAtel: /dev/ttyUSB2
	Run: roslaunch ntripclient ntripclient.launch
	Setup: Change the default setting in bncSettings.cpp
--------------------------------------------LOG--------------------------------------------
roslaunch ntripclient ntripclient.launch 
... logging to /root/.ros/log/96c1088c-7f35-11ee-96e3-f0d415b92d14/roslaunch-t0535zw23b-3714.log
Checking log directory for disk usage. This may take a while.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.

started roslaunch server http://t0535zw23b:44419/

SUMMARY
========

PARAMETERS
 * /ntripclient_node/password: 801655
 * /ntripclient_node/port: 9950
 * /ntripclient_node/serialport: 15
 * /ntripclient_node/server: mi.smartnetna.com
 * /ntripclient_node/username: ste01565018
 * /rosdistro: noetic
 * /rosversion: 1.15.15

NODES
  /
    ntripclient_node (ntripclient/ntripclient_node)

auto-starting new master
process[master]: started with pid [3737]
ROS_MASTER_URI=http://localhost:11311

setting /run_id to 96c1088c-7f35-11ee-96e3-f0d415b92d14
process[rosout-1]: started with pid [3762]
started core service [/rosout]
process[ntripclient_node-2]: started with pid [3769]
[ INFO] [1699557863.872648115]: Initializing nodelet with 16 worker threads.
[ WARN] [1699557863.879838770]: Initalizing Nodelet ntripclient
100000 bncMain entry
QStandardPaths: XDG_RUNTIME_DIR not set, defaulting to '/tmp/runtime-root'
 100012 setConfFileName /home/t0535zw/workspace/BNC_2.12.18/log/BNC02.bnc
 100015 bncSettings reRead /home/t0535zw/workspace/BNC_2.12.18/log/BNC02.bnc
  100017 in default 
 100300 bncGetThread: creating, //ste01565018:801655@mi.smartnetna.com:9950/RTCM3_IMAX_ITRF14, RTCM_3, 41.26, -96.14, yes, 1
 100310 bncGetThread initialize
  100345 this mountPoint RTCM3_IMAX_ITRF14
  100346 serialMountPoint RTCM3_IMAX_ITRF14
 100350 serialMountPoint is matched
 100360 bncGetThread initDecoder
QIODevice::write (QFile, "~/workspace/BNC_2.12.18/log/log_bnc_231109"): device not open
 100363 initDecoder Get data in RTCM 3.x format 
 100810 RTCM3Decoder created
 100400 bncGetThread: run --------------
  100500 tryReconnect
  100510 _ntripVersion 1
  100704 bncNetQueryV1 creating 
  100520 _serialPort read 176
  100600 bncNetQueryV1 startRequest
  100602 bncNetQueryV1 startRequestPrivate
  100610 startRequestPrivate GET /RTCM3_IMAX_ITRF14 HTTP/1.0
User-Agent: NTRIP BNC/2.12.18 (LINUX)
Host: mi.smartnetna.com
Authorization: Basic c3RlMDE1NjUwMTg6ODAxNjU1

$GPGGA,192248.20,4239.4476154,N,08313.7147880,W,4,25,0.8,283.621,M,-35.00,M,01,1180*6D

  100650 Read Caster Response ICY 200 OK

  100410 waitForReadyRead 
  100720 bncNetQueryV1 waitForReadyRead 39
  100415 _serialPort read  
  100700 slotSerialReadyRead
  100417 _serialPort write 
  100420 decoder()->Decode 
 100970 RTCM3Decoder Decode
 100400 bncGetThread: run --------------
  100500 tryReconnect
  100410 waitForReadyRead 
  100720 bncNetQueryV1 waitForReadyRead 0
  100720 bncNetQueryV1 waitForReadyRead 234
  100415 _serialPort read  
  100700 slotSerialReadyRead
  100705 sendNMEA $GPGGA,192424.50,4239.4476020,N,08313.7150088,W,2,13,0.8,283.289,M,-35.00,M,98,1180*67
  100712 bncNetQueryV1 keepAliveRequest
  100714 bncNetQueryV1 connectToHost
QAbstractSocket::connectToHost() called when already looking up or connecting/connected to "mi.smartnetna.com"
  100417 _serialPort write 
  100420 decoder()->Decode 
 100970 RTCM3Decoder Decode
 100975 Decode id 1004
 100820 RTCM3Decoder DecodeRTCM3GPS
 100975 Decode id 1012
 100860 RTCM3Decoder DecodeRTCM3GLONASS
 100400 bncGetThread: run --------------
  100500 tryReconnect
  100410 waitForReadyRead 
  100720 bncNetQueryV1 waitForReadyRead 0
  100720 bncNetQueryV1 waitForReadyRead 328
  100415 _serialPort read  
  100700 slotSerialReadyRead
  100705 sendNMEA $GPGGA,192425.40,4239.4476000,N,08313.7150121,W,2,13,0.8,283.301,M,-35.00,M,98,1180*66
  100712 bncNetQueryV1 keepAliveRequest
  100714 bncNetQueryV1 connectToHost
QAbstractSocket::connectToHost() called when already looking up or connecting/connected to "mi.smartnetna.com"
  100417 _serialPort write 
  100420 decoder()->Decode 
 100970 RTCM3Decoder Decode
 100975 Decode id 1008
 100950 RTCM3Decoder DecodeAntennaReceiver
 100975 Decode id 1033
 100950 RTCM3Decoder DecodeAntennaReceiver
 100975 Decode id 1230
 100840 RTCM3Decoder DecodeRTCM3MSM
 100975 Decode id 1004
 100820 RTCM3Decoder DecodeRTCM3GPS
 100975 Decode id 1012
 100860 RTCM3Decoder DecodeRTCM3GLONASS
 100400 bncGetThread: run --------------
  100500 tryReconnect
  100410 waitForReadyRead 
  100720 bncNetQueryV1 waitForReadyRead 0
  100720 bncNetQueryV1 waitForReadyRead 234
  100415 _serialPort read  
  100700 slotSerialReadyRead
  100705 sendNMEA $GPGGA,192426.40,4239.4475990,N,08313.7150144,W,2,13,0.8,283.303,M,-35.00,M,99,1180*66
  100712 bncNetQueryV1 keepAliveRequest
  100714 bncNetQueryV1 connectToHost
QAbstractSocket::connectToHost() called when already looking up or connecting/connected to "mi.smartnetna.com"
  100417 _serialPort write 
  100420 decoder()->Decode 
 100970 RTCM3Decoder Decode
 100975 Decode id 1004
 100820 RTCM3Decoder DecodeRTCM3GPS
 100975 Decode id 1012
 100860 RTCM3Decoder DecodeRTCM3GLONASS
 100400 bncGetThread: run --------------
  100500 tryReconnect
  100410 waitForReadyRead 
  100720 bncNetQueryV1 waitForReadyRead 0
  100720 bncNetQueryV1 waitForReadyRead 234
  100415 _serialPort read  
  100700 slotSerialReadyRead
  100705 sendNMEA $GPGGA,192427.40,4239.4475930,N,08313.7150191,W,2,13,0.8,283.307,M,-35.00,M,99,1180*61
  100712 bncNetQueryV1 keepAliveRequest
  100714 bncNetQueryV1 connectToHost
QAbstractSocket::connectToHost() called when already looking up or connecting/connected to "mi.smartnetna.com"
  100417 _serialPort write 
  100420 decoder()->Decode 
 100970 RTCM3Decoder Decode
 100975 Decode id 1004
 100820 RTCM3Decoder DecodeRTCM3GPS
 100975 Decode id 1012
 100860 RTCM3Decoder DecodeRTCM3GLONASS
 100400 bncGetThread: run --------------
  100500 tryReconnect
  100410 waitForReadyRead 
  100720 bncNetQueryV1 waitForReadyRead 0
  100720 bncNetQueryV1 waitForReadyRead 26
  100415 _serialPort read  
  100700 slotSerialReadyRead
  100705 sendNMEA $GPGGA,192428.60,4239.4475886,N,08313.7150296,W,2,13,0.8,283.308,M,-35.00,M,99,1180*6B
  100712 bncNetQueryV1 keepAliveRequest
  100714 bncNetQueryV1 connectToHost
QAbstractSocket::connectToHost() called when already looking up or connecting/connected to "mi.smartnetna.com"
  100417 _serialPort write 
  100420 decoder()->Decode 
 100970 RTCM3Decoder Decode
 100975 Decode id 1032
 100400 bncGetThread: run --------------
  100500 tryReconnect
  100410 waitForReadyRead 
  100720 bncNetQueryV1 waitForReadyRead 0
  100720 bncNetQueryV1 waitForReadyRead 261
  100415 _serialPort read  
  100700 slotSerialReadyRead
  100705 sendNMEA $GPGGA,192429.00,4239.4475871,N,08313.7150323,W,2,13,0.8,283.304,M,-35.00,M,99,1180*67
  100712 bncNetQueryV1 keepAliveRequest
  100714 bncNetQueryV1 connectToHost
QAbstractSocket::connectToHost() called when already looking up or connecting/connected to "mi.smartnetna.com"
  100417 _serialPort write 
  100420 decoder()->Decode 
 100970 RTCM3Decoder Decode
 100975 Decode id 1006
 100960 RTCM3Decoder DecodeAntennaPosition
 100975 Decode id 1004
 100820 RTCM3Decoder DecodeRTCM3GPS
 100975 Decode id 1012
 100860 RTCM3Decoder DecodeRTCM3GLONASS
 100400 bncGetThread: run --------------
  100500 tryReconnect
  100410 waitForReadyRead 
  100720 bncNetQueryV1 waitForReadyRead 0
  100720 bncNetQueryV1 waitForReadyRead 234
  100415 _serialPort read  
  100700 slotSerialReadyRead
  100705 sendNMEA $GPGGA,192429.40,4239.4475867,N,08313.7150318,W,2,13,0.8,283.323,M,-35.00,M,99,1180*69
  100712 bncNetQueryV1 keepAliveRequest
  100714 bncNetQueryV1 connectToHost
QAbstractSocket::connectToHost() called when already looking up or connecting/connected to "mi.smartnetna.com"
  100417 _serialPort write 
  100420 decoder()->Decode 
 100970 RTCM3Decoder Decode
 100975 Decode id 1004
 100820 RTCM3Decoder DecodeRTCM3GPS
 100975 Decode id 1012
 100860 RTCM3Decoder DecodeRTCM3GLONASS
 100400 bncGetThread: run --------------
  100500 tryReconnect
  100410 waitForReadyRead 
  100720 bncNetQueryV1 waitForReadyRead 0
  100720 bncNetQueryV1 waitForReadyRead 328
  100415 _serialPort read  
  100700 slotSerialReadyRead
  100705 sendNMEA $GPGGA,192430.60,4239.4475865,N,08313.7150297,W,2,13,0.8,283.338,M,-35.00,M,99,1180*6D
  100712 bncNetQueryV1 keepAliveRequest
  100714 bncNetQueryV1 connectToHost
QAbstractSocket::connectToHost() called when already looking up or connecting/connected to "mi.smartnetna.com"
  100417 _serialPort write 
  100420 decoder()->Decode 
 100970 RTCM3Decoder Decode
 100975 Decode id 1008
 100950 RTCM3Decoder DecodeAntennaReceiver
 100975 Decode id 1033
 100950 RTCM3Decoder DecodeAntennaReceiver
 100975 Decode id 1230
 100840 RTCM3Decoder DecodeRTCM3MSM
 100975 Decode id 1004
 100820 RTCM3Decoder DecodeRTCM3GPS
 100975 Decode id 1012
 100860 RTCM3Decoder DecodeRTCM3GLONASS
 100400 bncGetThread: run --------------
  100500 tryReconnect
  100410 waitForReadyRead 
  100720 bncNetQueryV1 waitForReadyRead 0
  100720 bncNetQueryV1 waitForReadyRead 234
  100415 _serialPort read  
  100700 slotSerialReadyRead
  100705 sendNMEA $GPGGA,192431.50,4239.4476060,N,08313.7147781,W,4,25,0.8,283.627,M,-35.00,M,02,1180*6F
  100712 bncNetQueryV1 keepAliveRequest
  100714 bncNetQueryV1 connectToHost
QAbstractSocket::connectToHost() called when already looking up or connecting/connected to "mi.smartnetna.com"
  100417 _serialPort write 
  100420 decoder()->Decode 
 100970 RTCM3Decoder Decode
 100975 Decode id 1004
 100820 RTCM3Decoder DecodeRTCM3GPS
 100975 Decode id 1012
 100860 RTCM3Decoder DecodeRTCM3GLONASS
 100400 bncGetThread: run --------------

