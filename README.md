# VMT - Virtual Motion Tracker の MocapForAll向け改造版

VMT - Virtual Motion Tracker を改造し、[デバイスの姿勢を取得するAPIを追加](https://github.com/KenjiAsaba/VirtualMotionTracker/commit/aa35bd98d5f569167222039a61ccab175c4761c3)したバージョンです。  
負荷分散のためにネットワーク上の別PCで実行しているSteamVRからデバイスの姿勢を取得したいという[MocapForAll](https://github.com/Akiya-Research-Institute/MocapForAll-Wiki/wiki#%E7%9B%AE%E6%AC%A1)での利用を念頭にしたものですが、場合によっては他の用途にも使えるかもしれません。

## オリジナル版からの変更点

ドライバに対する操作に、下記が追加されています。

- **/VMT/GetDevicePose serial**
  指定したシリアル番号のデバイスの姿勢の返送を要求します。
  「serial」は、string型でデバイスシリアル(LHR-xxxxxxx等)を指定します。ヘッドマウントディスプレイに対しては、デバイスシリアルの代わりに「HMD」と指定することができます。

ドライバからの応答に、下記が追加されています。

- **/VMT/DevicePose serial x, y, z, qx, qy, qz, qw**
  シリアル番号で特定されるデバイスの姿勢を通知します。

上記以外は、[オリジナル版](https://gpsnmeajp.github.io/VirtualMotionTrackerDocument/)と同じです。

# Licence
MIT Licence

Logo text font: M+ Fonts https://mplus-fonts.osdn.jp/about2.html
