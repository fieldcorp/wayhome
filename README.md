# WAYHOME companion

A phone web page that sends your location to the WAYHOME keychain over Bluetooth, so its glowing arrow can point home.

**Open it:** https://fieldcorp.github.io/wayhome/

## Use it

1. Open the page on your phone:
   - **Android:** Chrome
   - **iPhone:** the free **Bluefy** browser (Safari can't use Bluetooth from a web page)
2. Wake the device, tap **Connect to WAYHOME**, and pick it from the list.
3. Allow location access.
4. Tap **Set home to where I am now**, or paste coordinates and tap **Save**.

Keep the page open while you walk: browsers pause Bluetooth for pages in the background.

## How it talks to the device

The device advertises a Bluetooth LE service. The page writes plain text `lat,lon` to two characteristics:

| What | UUID |
|---|---|
| Service | `dc68c2d7-d4f8-466f-b225-025be6893389` |
| Your position (write, every 2 s) | `8732c491-619e-4fcd-8a7d-be54e36ac17d` |
| Home (read / write) | `60949155-f5ed-4533-afe4-311cdbc9fde2` |
