I installed OBS Studio on my new laptop (Intel i5-11400H + Nvidia GTX 1650), and when I tried to record, I encountered the following error:

> Failed to start recording/streaming
> Starting the output failed. Please check the log for details.
> 
> Note: If you're using NVENC or AMD encoders, make sure your video drivers are up to date.

To get a clearer picture of the problem, I launched OBS from the terminal. This is what I saw:

> [qsv encoder: 'msdk_impl'] Specified object/item/sync point not found. (MFX_ERR_NOT_FOUND)
> 
> [qsv encoder: 'simple_video_recording'] qsv failed to load

After searching online, I found that this issue is caused by the lack of drivers for the [Intel Quick Sync Video](https://en.wikipedia.org/wiki/Intel_Quick_Sync_Video) (QSV), a video encoding and decoding hardware core present in some Intel CPUs.

As a workaround, I saw someone suggest two possible solutions for a Windows user:

1. Selecting the Software (x264) encoder in Settings > Output > Recording > Encoder.

2. Downgrading OBS to version v29.1.3, which was the last to support older CPUs and the legacy QSV encoder.

However, these options don't seem ideal to me as the first one can cause performance issues, and the second is simply not appealing to me because I prefer using the latest version of OBS.

But if you're on Arch Linux you don't have to worry, because there’s a much better solution: You can **simply install the intel-media-sdk package** from the extra repository. According to its description, it’s a “Legacy API for hardware video acceleration on Intel GPUs (Broadwell to Rocket Lake).”

After installing it and restarting OBS, everything worked perfectly.
