
---

# W키 전진 속도 분석

## W키 로그 데이터
* Serving Flask app '__main__'
 * Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5000
 * Running on http://192.168.0.124:5000
Press CTRL+C to quit
127.0.0.1 - - [08/Apr/2025 13:09:25] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:25] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:25] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085365.7268872
Updated Position: (59, 27)
127.0.0.1 - - [08/Apr/2025 13:09:27] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:27] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:27] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:27] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:27] "POST /update_position HTTP/1.1" 200 -
Updated Position: (59, 27)Sent Move Command: W at 1744085367.6226923

Updated Position: (59, 27)
127.0.0.1 - - [08/Apr/2025 13:09:27] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:27] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:27] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:27] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085367.8193436
Sent Move Command: W at 1744085367.9889822
Updated Position: (59, 27)
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_move HTTP/1.1" 200 -
Sent Move Command: W at 1744085368.153474
Updated Position: (59, 27)
Updated Position: (59, 28)
Sent Move Command: W at 1744085368.3225598
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "POST /info HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_move HTTP/1.1" 200 -
Sent Move Command: W at 1744085368.4931042
Updated Position: (59, 28)
Received /info data: {'time': 1.0049320459365845, 'distance': 259.8588562011719, 'playerPos': {'x': 59.35000228881836, 'y': 7.993528366088867, 'z': 28.407678604125977}, 'playerSpeed': 1.5415621995925903, 'playerHealth': 100.0, 'playerTurretX': 2.9181717042803257e-09, 'playerTurretY': 0.0, 'playerBodyX': 2.9181717042803257e-09, 'playerBodyY': -3.256887814995224e-11, 'enemyPos': {'x': 135.46002197265625, 'y': 8.599621772766113, 'z': 276.8699951171875}, 'enemySpeed': 0.3984132409095764, 'enemyHealth': 100.0, 'enemyTurretX': 179.99974060058594, 'enemyTurretY': -0.01585240848362446, 'enemyBodyX': 179.99974060058594, 'enemyBodyY': 0.01585240848362446}
Updated Position: (59, 28)
Sent Move Command: W at 1744085368.6508815
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:28] "POST /update_position HTTP/1.1" 200 -
Updated Position: (59, 29)
Sent Move Command: W at 1744085368.8286395
Sent Move Command: W at 1744085368.9727144
Updated Position: (59, 29)
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "POST /update_position HTTP/1.1" 200 -
Updated Position: (59, 30)
Sent Move Command: W at 1744085369.1554422
Sent Move Command: W at 1744085369.3231742
Updated Position: (59, 31)
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "POST /info HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "POST /update_position HTTP/1.1" 200 -
Updated Position: (59, 32)
Sent Move Command: W at 1744085369.4970176
Received /info data: {'time': 2.0061705112457275, 'distance': 256.4068908691406, 'playerPos': {'x': 59.349998474121094, 'y': 7.991300582885742, 'z': 32.02027893066406}, 'playerSpeed': 3.6081326007843018, 'playerHealth': 100.0, 'playerTurretX': 2.9181717042803257e-09, 'playerTurretY': 0.0, 'playerBodyX': 2.9181717042803257e-09, 'playerBodyY': -3.256887814995224e-11, 'enemyPos': {'x': 135.4600067138672, 'y': 8.599720001220703, 'z': 276.8699951171875}, 'enemySpeed': 9.928358485922217e-05, 'enemyHealth': 100.0, 'enemyTurretX': 180.0001983642578, 'enemyTurretY': -8.22708461782895e-05, 'enemyBodyX': 180.0001983642578, 'enemyBodyY': 8.22708461782895e-05}
Command: W, Speed Change: 0.5740 m/s, Time Diff: 1.0012 s, Acceleration: 0.5733 m/s^2
Sent Move Command: W at 1744085369.658925
Updated Position: (59, 32)
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:29] "GET /get_move HTTP/1.1" 200 -
Sent Move Command: W at 1744085369.8143218
Updated Position: (59, 33)
Updated Position: (59, 34)
Sent Move Command: W at 1744085369.9850886
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085370.1444056
Updated Position: (59, 35)
Sent Move Command: W at 1744085370.3081276
Updated Position: (59, 36)
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "POST /info HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "POST /update_position HTTP/1.1" 200 -
Updated Position: (59, 37)
Sent Move Command: W at 1744085370.4807348
Received /info data: {'time': 3.0394439697265625, 'distance': 250.42156982421875, 'playerPos': {'x': 59.35011291503906, 'y': 7.990752696990967, 'z': 38.29531478881836}, 'playerSpeed': 6.072967052459717, 'playerHealth': 100.0, 'playerTurretX': 0.00019426194194238633, 'playerTurretY': 0.149169921875, 'playerBodyX': 0.00019426194194238633, 'playerBodyY': 359.850830078125, 'enemyPos': {'x': 135.4600067138672, 'y': 8.599989891052246, 'z': 276.8699951171875}, 'enemySpeed': 0.00026119884569197893, 'enemyHealth': 100.0, 'enemyTurretX': 179.99974060058594, 'enemyTurretY': -0.00011828762217191979, 'enemyBodyX': 179.99974060058594, 'enemyBodyY': 0.00011828762217191979}
Command: W, Speed Change: 0.6847 m/s, Time Diff: 1.0333 s, Acceleration: 0.6626 m/s^2
Sent Move Command: W at 1744085370.6512694
Updated Position: (59, 39)
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:30] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085370.8152769
Updated Position: (59, 40)
Sent Move Command: W at 1744085370.981226
Updated Position: (59, 41)
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_move HTTP/1.1" 200 -
Sent Move Command: W at 1744085371.1438696
Updated Position: (59, 43)
Sent Move Command: W at 1744085371.3151457
Updated Position: (59, 44)
127.0.0.1 - - [08/Apr/2025 13:09:31] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "POST /info HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085371.4957228
Updated Position: (59, 46)
Received /info data: {'time': 4.050765037536621, 'distance': 242.20359802246094, 'playerPos': {'x': 59.362144470214844, 'y': 8.413899421691895, 'z': 46.931617736816406}, 'playerSpeed': 8.549877166748047, 'playerHealth': 100.0, 'playerTurretX': 0.2749062180519104, 'playerTurretY': 5.529876708984375, 'playerBodyX': 0.2749062180519104, 'playerBodyY': 354.4701232910156, 'enemyPos': {'x': 135.4600067138672, 'y': 8.599985122680664, 'z': 276.8699951171875}, 'enemySpeed': 4.714992883236846e-06, 'enemyHealth': 100.0, 'enemyTurretX': 179.99974060058594, 'enemyTurretY': -0.0002876964572351426, 'enemyBodyX': 179.99974060058594, 'enemyBodyY': 0.0002876964572351426}
Command: W, Speed Change: 0.6880 m/s, Time Diff: 1.0113 s, Acceleration: 0.6803 m/s^2
Sent Move Command: W at 1744085371.6630852
Updated Position: (59, 48)
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:31] "GET /get_move HTTP/1.1" 200 -
Updated Position: (59, 49)
Sent Move Command: W at 1744085371.8247766
Updated Position: (59, 51)
Sent Move Command: W at 1744085371.9922957
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085372.1601293
Updated Position: (59, 53)
Sent Move Command: W at 1744085372.33725
Updated Position: (59, 55)
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "POST /info HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "POST /update_position HTTP/1.1" 200 -
Updated Position: (59, 57)
Sent Move Command: W at 1744085372.501781
Received /info data: {'time': 5.062398910522461, 'distance': 231.7206268310547, 'playerPos': {'x': 59.47779083251953, 'y': 10.111230850219727, 'z': 57.96622085571289}, 'playerSpeed': 11.036581993103027, 'playerHealth': 100.0, 'playerTurretX': 0.7009974718093872, 'playerTurretY': 8.884765625, 'playerBodyX': 0.7009974718093872, 'playerBodyY': 351.115234375, 'enemyPos': {'x': 135.4600067138672, 'y': 8.599733352661133, 'z': 276.8699951171875}, 'enemySpeed': 0.0002488746540620923, 'enemyHealth': 100.0, 'enemyTurretX': 179.99966430664062, 'enemyTurretY': -0.009907597675919533, 'enemyBodyX': 179.99966430664062, 'enemyBodyY': 0.009907597675919533}
Command: W, Speed Change: 0.6908 m/s, Time Diff: 1.0116 s, Acceleration: 0.6828 m/s^2
Updated Position: (59, 59)
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:32] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085372.6795478
Sent Move Command: W at 1744085372.838597
Updated Position: (59, 61)
127.0.0.1 - - [08/Apr/2025 13:09:32] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_move HTTP/1.1" 200 -
Sent Move Command: W at 1744085373.00543
Updated Position: (59, 63)
Updated Position: (59, 66)
Sent Move Command: W at 1744085373.1788518
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_move HTTP/1.1" 200 -
Updated Position: (59, 68)
Sent Move Command: W at 1744085373.359165
Updated Position: (59, 71)
Sent Move Command: W at 1744085373.535312
127.0.0.1 - - [08/Apr/2025 13:09:33] "POST /info HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "POST /update_position HTTP/1.1" 200 -
Received /info data: {'time': 6.079041957855225, 'distance': 218.8525390625, 'playerPos': {'x': 59.44374084472656, 'y': 10.13621711730957, 'z': 71.64913940429688}, 'playerSpeed': 13.458985328674316, 'playerHealth': 100.0, 'playerTurretX': 359.4561767578125, 'playerTurretY': -5.747535228729248, 'playerBodyX': 359.4561767578125, 'playerBodyY': 5.747535228729248, 'enemyPos': {'x': 135.4600067138672, 'y': 8.59998893737793, 'z': 276.8699951171875}, 'enemySpeed': 0.00025140063371509314, 'enemyHealth': 100.0, 'enemyTurretX': 179.9996795654297, 'enemyTurretY': -0.00011696987348841503, 'enemyBodyX': 179.9996795654297, 'enemyBodyY': 0.00011696987348841503}
Command: W, Speed Change: 0.6729 m/s, Time Diff: 1.0166 s, Acceleration: 0.6619 m/s^2
Sent Move Command: W at 1744085373.6819487
Updated Position: (59, 73)
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:33] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085373.8519711
Updated Position: (59, 76)
Sent Move Command: W at 1744085374.0223534
Updated Position: (59, 78)
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085374.1889417
Updated Position: (59, 81)
Updated Position: (59, 84)
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "POST /info HTTP/1.1" 200 -
Sent Move Command: W at 1744085374.3761907
Sent Move Command: W at 1744085374.5348308
Updated Position: (59, 87)
Received /info data: {'time': 7.0910964012146, 'distance': 203.87913513183594, 'playerPos': {'x': 59.30879211425781, 'y': 9.13312816619873, 'z': 87.74726104736328}, 'playerSpeed': 15.937786102294922, 'playerHealth': 100.0, 'playerTurretX': 359.3983459472656, 'playerTurretY': -4.918584823608398, 'playerBodyX': 359.3983459472656, 'playerBodyY': 4.918584823608398, 'enemyPos': {'x': 135.4600067138672, 'y': 8.599824905395508, 'z': 276.8699951171875}, 'enemySpeed': 0.000162078213179484, 'enemyHealth': 100.0, 'enemyTurretX': 179.9997100830078, 'enemyTurretY': -0.007166991475969553, 'enemyBodyX': 179.9997100830078, 'enemyBodyY': 0.007166991475969553}
Command: W, Speed Change: 0.6886 m/s, Time Diff: 1.0121 s, Acceleration: 0.6804 m/s^2
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:34] "POST /update_position HTTP/1.1" 200 -
Updated Position: (59, 89)
Sent Move Command: W at 1744085374.7011995
Sent Move Command: W at 1744085374.876205
Updated Position: (59, 92)
127.0.0.1 - - [08/Apr/2025 13:09:34] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085375.0496447
Updated Position: (59, 96)
Sent Move Command: W at 1744085375.2076104
Updated Position: (59, 99)
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085375.389049
Updated Position: (59, 102)
Sent Move Command: W at 1744085375.5594969
Updated Position: (59, 105)
127.0.0.1 - - [08/Apr/2025 13:09:35] "POST /info HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "POST /update_position HTTP/1.1" 200 -
Received /info data: {'time': 8.116966247558594, 'distance': 186.58827209472656, 'playerPos': {'x': 59.12873077392578, 'y': 8.581095695495605, 'z': 106.60924530029297}, 'playerSpeed': 18.395042419433594, 'playerHealth': 100.0, 'playerTurretX': 359.4530944824219, 'playerTurretY': 0.536376953125, 'playerBodyX': 359.4530944824219, 'playerBodyY': 359.463623046875, 'enemyPos': {'x': 135.4600067138672, 'y': 8.599760055541992, 'z': 276.8699951171875}, 'enemySpeed': 6.321450200630352e-05, 'enemyHealth': 100.0, 'enemyTurretX': 179.99974060058594, 'enemyTurretY': -0.0001329964870819822, 'enemyBodyX': 179.99974060058594, 'enemyBodyY': 0.0001329964870819822}
Command: W, Speed Change: 0.6826 m/s, Time Diff: 1.0259 s, Acceleration: 0.6654 m/s^2
Sent Move Command: W at 1744085375.7225335
Updated Position: (59, 109)
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:35] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_move HTTP/1.1" 200 -
Sent Move Command: W at 1744085375.9087498
Updated Position: (59, 112)
Sent Move Command: W at 1744085376.081764
127.0.0.1 - - [08/Apr/2025 13:09:36] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_move HTTP/1.1" 200 -
Updated Position: (59, 115)
Updated Position: (59, 119)
Sent Move Command: W at 1744085376.2646985
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "POST /info HTTP/1.1" 200 -
Updated Position: (58, 122)
Sent Move Command: W at 1744085376.4321086
Sent Move Command: W at 1744085376.6016123
Updated Position: (58, 125)
Received /info data: {'time': 9.159109115600586, 'distance': 168.4693145751953, 'playerPos': {'x': 58.919456481933594, 'y': 9.96082878112793, 'z': 126.79803466796875}, 'playerSpeed': 19.418607711791992, 'playerHealth': 100.0, 'playerTurretX': 359.3988037109375, 'playerTurretY': 4.582305908203125, 'playerBodyX': 359.3988037109375, 'playerBodyY': 355.4176940917969, 'enemyPos': {'x': 135.4600067138672, 'y': 8.596084594726562, 'z': 276.8699951171875}, 'enemySpeed': 0.0035268301144242287, 'enemyHealth': 100.0, 'enemyTurretX': 179.99986267089844, 'enemyTurretY': -0.17325526475906372, 'enemyBodyX': 179.99986267089844, 'enemyBodyY': 0.17325526475906372}
Command: W, Speed Change: 0.2843 m/s, Time Diff: 1.0421 s, Acceleration: 0.2728 m/s^2
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:36] "POST /update_position HTTP/1.1" 200 -
Sent Move Command: W at 1744085376.7693517
Updated Position: (58, 129)
Sent Move Command: W at 1744085376.9484093
Updated Position: (58, 132)
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_move HTTP/1.1" 200 -
Sent Move Command: W at 1744085377.122051
Updated Position: (58, 136)
Sent Move Command: W at 1744085377.3099916
127.0.0.1 - - [08/Apr/2025 13:09:37] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "POST /update_position HTTP/1.1" 200 -
Updated Position: (58, 139)
Sent Move Command: W at 1744085377.4906292
Updated Position: (58, 143)
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "POST /info HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:37] "POST /update_position HTTP/1.1" 200 -
Received /info data: {'time': 10.178459167480469, 'distance': 151.3092498779297, 'playerPos': {'x': 58.68255615234375, 'y': 12.078636169433594, 'z': 146.53346252441406}, 'playerSpeed': 19.473337173461914, 'playerHealth': 100.0, 'playerTurretX': 359.2294616699219, 'playerTurretY': 6.903564453125, 'playerBodyX': 359.2294616699219, 'playerBodyY': 353.096435546875, 'enemyPos': {'x': 135.4600067138672, 'y': 8.599991798400879, 'z': 276.8699951171875}, 'enemySpeed': 0.003833034308627248, 'enemyHealth': 100.0, 'enemyTurretX': 179.99996948242188, 'enemyTurretY': -2.7791591492132284e-05, 'enemyBodyX': 179.99996948242188, 'enemyBodyY': 2.7791591492132284e-05}
Command: W, Speed Change: 0.0152 m/s, Time Diff: 1.0194 s, Acceleration: 0.0149 m/s^2
Sent Move Command: stop at 1744085377.669709
Updated Position: (58, 146)
Updated Position: (58, 149)
127.0.0.1 - - [08/Apr/2025 13:09:37] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "POST /update_position HTTP/1.1" 200 -
Updated Position: (58, 152)
Updated Position: (58, 153)
127.0.0.1 - - [08/Apr/2025 13:09:38] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "POST /update_position HTTP/1.1" 200 -
Updated Position: (58, 153)
Updated Position: (58, 153)
127.0.0.1 - - [08/Apr/2025 13:09:38] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "POST /info HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "GET /get_action HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "POST /update_position HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "GET /get_move HTTP/1.1" 200 -
127.0.0.1 - - [08/Apr/2025 13:09:38] "GET /get_action HTTP/1.1" 200 -
Received /info data: {'time': 11.203041076660156, 'distance': 145.033203125, 'playerPos': {'x': 58.58251953125, 'y': 13.035444259643555, 'z': 153.9684295654297}, 'playerSpeed': 7.317080020904541, 'playerHealth': 100.0, 'playerTurretX': 359.1055603027344, 'playerTurretY': 11.701507568359375, 'playerBodyX': 359.1055603027344, 'playerBodyY': 348.2984924316406, 'enemyPos': {'x': 135.4600067138672, 'y': 8.598670959472656, 'z': 276.8699951171875}, 'enemySpeed': 0.0012891491642221808, 'enemyHealth': 100.0, 'enemyTurretX': 180.0, 'enemyTurretY': -0.05664760246872902, 'enemyBodyX': 180.0, 'enemyBodyY': 0.05664760246872902}
Command: stop, Speed Change: -3.3767 m/s, Time Diff: 1.0246 s, Acceleration: -3.2957 m/s^2
Updated Position: (58, 153)

## 단일 `W` 키 입력에 대한 탱크 반응

### 분석 결과
- **W 키 한 번 입력**:
  - **가속**: 약 0.65 m/s²로, 0.1초 동안 작용하는 것으로 보임.
  - **속도 증가**: 약 0.065 m/s (≈ 0.234 km/h)로 계산됨.
  - **이동 거리**: 약 0.0033 m (≈ 3.3 mm)로 추정됨.
  - **이후**: 가속이 멈춘 후 즉시 정지하며, 관성에 의한 이동은 미미한 수준으로, 로그상 위치 변화가 1단위 미만으로 나타남.

- **물리적 결과**:
  - **힘**: 약 36.4 kN으로 계산됨.
  - **출력**: 약 3.17 hp로, 0.1초 동안 작용하는 것으로 사료됨.

### 결론
- **단일 `W` 입력 반응**: 시뮬레이터에서 `W` 키 한 번 입력 시 탱크가 약 0.65 m/s²의 가속도로 0.1초간 가속되며, 속도는 약 0.234 km/h, 이동 거리는 약 3.3 mm로 나타남. 이후 즉시 정지하는 것으로 보임.
- **현실성**: 56톤 탱크가 0.1초 가속으로 이동한 거리가 매우 작아 시뮬레이터의 최소 단위(1m) 미만이므로, 눈에 띄는 위치 변화는 없는 것으로 사료됨.

---

# A 키 회전 속도 분석

## 로그 데이터 기반 분석
로그에서 `/get_move` 호출을 살펴보면, "A" 키가 약 0.15~0.2초 간격으로 입력되는 것으로 보임:
- 예: `1744098902.085294` → `1744098903.0916896` (약 1초 간격 내 여러 호출 발생, 평균 0.15~0.2초 간격으로 추정됨).
- 다만, 질문에서 "0.1초당 A 키 입력"을 가정하라고 했으므로 이를 기준으로 계산함.

### 각가속도 분석
각가속도는 연속된 각속도 차이를 시간 차이로 나눈 값으로, 로그에서 아래와 같은 값이 계산됨:
- 0.0568 deg/s², 0.2470 deg/s², -0.2569 deg/s², 0.0994 deg/s², 0.0304 deg/s², -0.0221 deg/s², -0.0528 deg/s², 0.1666 deg/s²

평균 각가속도는 다음과 같이 계산됨:
- 평균 각가속도 ≈ (0.0568 + 0.2470 + (-0.2569) + 0.0994 + 0.0304 + (-0.0221) + (-0.0528) + 0.1666) / 8 ≈ 0.0335 deg/s²

### "A" 키 입력과 시간 관계
- 로그에서 `/info` 호출 간격은 약 1초로 보이며, 이 동안 "A" 키 입력이 약 5~6회 발생하는 것으로 추정됨 (0.15~0.2초 간격).
- 0.1초당 "A" 키 입력을 가정하면, 1초에 10번 입력되는 것으로 계산 가능함.

### 0.1초당 각가속도 할당 계산
- 평균 각가속도: 0.0335 deg/s² (1초 동안 발생).
- 1초에 "A" 키가 10번 입력된다고 가정 시:
  - 0.1초당 각가속도 = 0.0335 / 10 ≈ 0.00335 deg/s²
- 실제 로그에서 입력 간격이 0.15~0.2초로 보이므로, 이를 반영하면:
  - 1초에 약 5번 입력 가정 시: 0.2초당 각가속도 = 0.0335 / 5 ≈ 0.0067 deg/s²
  - 0.1초로 환산: 0.0067 / 2 ≈ 0.00335 deg/s²
- 두 계산 결과가 일치하는 것으로 나타남.

### "A" 키 한 번 입력당 각가속도
- 평균 각가속도 0.0335 deg/s²는 1초 동안의 총합으로 보임.
- "A" 키 입력 간격이 약 0.15~0.2초로 추정되므로:
  - 1초에 5번 입력 가정 시: 한 번 입력당 0.0335 / 5 ≈ 0.0067 deg/s²
  - 0.1초로 환산: 0.0067 / 2 ≈ 0.00335 deg/s²

### 최종 결과
- **질문**: 0.1초당 "A" 키 입력 시, "A" 키 한 번 입력당 얼마의 각가속도가 할당되는가?
- **답변**: 로그 데이터와 평균을 기반으로, "A" 키 한 번 입력당 약 0.0067 deg/s²의 각가속도가 발생하는 것으로 보이며, 이를 0.1초로 환산하면 약 0.00335 deg/s²로 계산됨.
- **추가**: 평균 각속도 -0.6983 rad/s는 초당 약 0.6983 라디안(≈ 40도) 회전하는 속도를 의미하는 것으로 사료됨.

---

# 터렛 고각에 따른 사격 거리

## 현재 전차 위치
- x: 59.3499, y: 7.9732, z: 27.2270

## 포신 각도별 피탄지 좌표 및 거리 계산

### 1. playerTurretY: 0.0
- **피탄지**: (59.37004, 9.200581, 53.90345)
- **거리 계산**:  
  d = √[(59.37004 - 59.3499)² + (9.200581 - 7.9732)² + (53.90345 - 27.2270)²]  
  ≈ √[0.004056 + 1.506464 + 711.6320] ≈ √713.1425 ≈ 26.7047

### 2. playerTurretY: -4.9999
- **피탄지**: (59.37004, 8.161985, 45.99543)
- **거리 계산**:  
  d = √[(59.37004 - 59.3499)² + (8.161985 - 7.9732)² + (45.99543 - 27.2270)²]  
  ≈ √[0.004056 + 0.035639 + 352.2540] ≈ √352.2937 ≈ 18.7695

### 3. playerTurretY: 5.2005
- **피탄지**: (59.37004, 8.456475, 105.1118)
- **거리 계산**:  
  d = √[(59.37004 - 59.3499)² + (8.456475 - 7.9732)² + (105.1118 - 27.2270)²]  
  ≈ √[0.004056 + 0.233555 + 6066.039] ≈ √6066.2766 ≈ 77.8862

### 4. playerTurretY: 10.0
- **피탄지**: (59.37004, 10.98848, 138.4616)
- **거리 계산**:  
  d = √[(59.37004 - 59.3499)² + (10.98848 - 7.9732)² + (138.4616 - 27.2270)²]  
  ≈ √[0.004056 + 9.091914 + 12373.14] ≈ √12382.24 ≈ 111.2746

### 결과 정리
| 포신 각도 (playerTurretY) | 피탄지 좌표 (X, Y, Z)          | 거리 (단위: 좌표계 기준) |
|---------------------------|--------------------------------|--------------------------|
| 0.0                       | (59.37004, 9.200581, 53.90345) | 약 26.7047              |
| -4.9999                   | (59.37004, 8.161985, 45.99543) | 약 18.7695              |
| 5.2005                    | (59.37004, 8.456475, 105.1118) | 약 77.8862              |
| 10.0                      | (59.37004, 10.98848, 138.4616) | 약 111.2746             |

### 최종 공식
각도 θ (도 단위)에 따른 피탄지 거리 d는 다음과 같은 2차 함수로 근사되는 것으로 보임:  
- **d(θ) = 0.8092θ² + 5.6334θ + 26.7047**  
  - θ: 포신 각도 (도, playerTurretY)  
  - d: 전차 위치에서 피탄지까지의 3D 거리

---

위 내용은 제공된 데이터를 기반으로 정리한 것으로, 시뮬레이터의 특성과 로그를 분석하여 도출된 결과로 사료됩니다. 추가 질문이나 보완이 필요하면 말씀해주세요!