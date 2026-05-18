[INFO ] ggml_extend.hpp:63   - ggml-dx12: Found 3 D3D12 device(s)
[DEBUG] util.cpp:713  - Found 4 backend devices:
[DEBUG] util.cpp:716  - #0: DX120
[DEBUG] util.cpp:716  - #1: DX121
[DEBUG] util.cpp:716  - #2: DX122
[DEBUG] util.cpp:716  - #3: CPU
[DEBUG] ggml_extend.hpp:110  - Initializing backend: DX120
[INFO ] stable-diffusion.cpp:212  - loading model from 'd:\llama.cpp\models\sd\gguf\LCM_Dreamshaper_v7-f16.gguf'
[INFO ] model.cpp:216  - load d:\llama.cpp\models\sd\gguf\LCM_Dreamshaper_v7-f16.gguf using gguf format
[DEBUG] model.cpp:265  - init from 'd:\llama.cpp\models\sd\gguf\LCM_Dreamshaper_v7-f16.gguf'
[INFO ] stable-diffusion.cpp:305  - Version: SD 1.x
[INFO ] stable-diffusion.cpp:333  - Weight type stat:                      f32: 703  |     f16: 428
[INFO ] stable-diffusion.cpp:334  - Conditioner weight type stat:          f32: 122  |     f16: 74
[INFO ] stable-diffusion.cpp:335  - Diffusion model weight type stat:      f32: 404  |     f16: 282
[INFO ] stable-diffusion.cpp:336  - VAE weight type stat:                  f32: 176  |     f16: 72
[DEBUG] stable-diffusion.cpp:338  - ggml tensor size = 400 bytes
[DEBUG] clip_tokenizer.cpp:65   - vocab size: 49408
[DEBUG] ggml_extend.hpp:2631 - clip params backend buffer size =  235.06 MB(VRAM) (196 tensors)
[DEBUG]ggml_extend.hpp:2631 - unet params backend buffer size =  1640.25 MB(VRAM) (686 tensors)
[INFO ] stable-diffusion.cpp:640  - using VAE for encoding / decoding
[INFO ] auto_encoder_kl.hpp:525  - vae decoder: ch = 128
[DEBUG] ggml_extend.hpp:2631 - vae params backend buffer size =  94.47 MB(VRAM) (140 tensors)
[DEBUG] stable-diffusion.cpp:766  - loading weights
[DEBUG] model.cpp:742  - using 96 threads for model loading
[DEBUG] model.cpp:764  - loading tensors from d:\llama.cpp\models\sd\gguf\LCM_Dreamshaper_v7-f16.gguf
  |==================================================| 1131/1131 - 1.66GB/s
[INFO ] model.cpp:999  - loading tensors completed, taking 1.39s (process: 0.23s, read: 0.49s, memcpy: 0.00s, convert: 0.00s, copy_to_backend: 0.03s)
[DEBUG] stable-diffusion.cpp:806  - finished loaded file
[INFO ] stable-diffusion.cpp:873  - total params memory size = 1969.78MB (VRAM 1969.78MB, RAM 0.00MB): text_encoders 235.06MB(VRAM), diffusion_model 1640.25MB(VRAM), vae 94.47MB(VRAM), controlnet 0.00MB(VRAM), pmid 0.00MB(VRAM)
[INFO ] stable-diffusion.cpp:931  - running in eps-prediction mode
[INFO ] stable-diffusion.cpp:3367 - generate_image 512x512
[INFO ] denoiser.hpp:539  - get_sigmas with LCM scheduler
[INFO ] stable-diffusion.cpp:2814 - sampling using LCM method
[DEBUG] conditioner.hpp:415  - parse 'an old man face in the rain' to [['an old man face in the rain', 1], ]
[DEBUG] bpe_tokenizer.cpp:183  - split prompt "an old man face in the rain" to tokens ["an</w>", "old</w>", "man</w>", "face</w>", "in</w>", "the</w>", "rain</w>", ]
[DEBUG] ggml_extend.hpp:1924 - clip compute buffer size: 1.42 MB(VRAM)
[INFO ] ggml_extend.hpp:63   - ggml-dx12: Auto-tune v9 loaded: Q4_K_dp4a=256t Q5_K_dp4a=256t F16_mr=256t (K>=633 uses 256t)
[DEBUG] conditioner.hpp:541  - computing condition graph completed, taking 22 ms
[DEBUG] conditioner.hpp:415  - parse '' to [['', 1], ]
[DEBUG] bpe_tokenizer.cpp:183  - split prompt "" to tokens []
[DEBUG] ggml_extend.hpp:1924 - clip compute buffer size: 1.42 MB(VRAM)
[DEBUG] conditioner.hpp:541  - computing condition graph completed, taking 10 ms
[INFO ] stable-diffusion.cpp:3168 - get_learned_condition completed, taking 0.04s
[INFO ] stable-diffusion.cpp:3401 - generating image: 1/1 - seed 42
[DEBUG] ggml_extend.hpp:1924 - unet compute buffer size: 559.90 MB(VRAM)
[WARN ] ggml_extend.hpp:2403 - unet missing GPU shader path for op TIMESTEP_EMBEDDING; falling back to CPU for this graph

0:000> k
Child-SP          RetAddr           Call Site
000000de`2771cbe8 00007ff6`d235ebd4 sd_cli!ggml_get_first_tensor [D:\llama.cpp\sd.cpp\ggml\src\ggml.c @ 1913]
000000de`2771cbf0 00007ff6`d236f01b sd_cli!ggml_tensor_num+0x14 [D:\llama.cpp\sd.cpp\src\ggml_extend.hpp @ 1656]
000000de`2771cc20 00007ff6`d221cdfb sd_cli!GGMLRunner::offload_all_params+0x5b [D:\llama.cpp\sd.cpp\src\ggml_extend.hpp @ 2070]
000000de`2771cce0 00007ff6`d2214711 sd_cli!GGMLRunner::execute_graph<float>+0x34b [D:\llama.cpp\sd.cpp\src\ggml_extend.hpp @ 2418]
000000de`2771ce70 00007ff6`d22e5464 sd_cli!GGMLRunner::compute<float>+0x861 [D:\llama.cpp\sd.cpp\src\ggml_extend.hpp @ 2748]
(Inline Function) --------`-------- sd_cli!UNetModelRunner::compute+0xbb [D:\llama.cpp\sd.cpp\src\unet.hpp @ 682]
000000de`2771cf90 00007ff6`d22acc6b sd_cli!UNetModel::compute+0x1c4 [D:\llama.cpp\sd.cpp\src\diffusion_model.hpp @ 115]
000000de`2771d100 00007ff6`d22adddf sd_cli!<lambda_cdb10b48dc3dba5623f3c3b5c87c4706>::operator()+0x12b [D:\llama.cpp\sd.cpp\src\stable-diffusion.cpp @ 1694]
000000de`2771d1c0 00007ff6`d22c88b4 sd_cli!<lambda_dd37c28d4b44de556076b849cdfc87b6>::operator()+0xb6f [D:\llama.cpp\sd.cpp\src\stable-diffusion.cpp @ 1705]
(Inline Function) --------`-------- sd_cli!std::invoke+0x1e [C:\Program Files\Microsoft Visual Studio\18\Community\VC\Tools\MSVC\14.50.35717\include\type_traits @ 1688]
000000de`2771d6e0 00007ff6`d2396433 sd_cli!std::_Func_impl_no_alloc<<lambda_dd37c28d4b44de556076b849cdfc87b6>,sd::Tensor<float>,sd::Tensor<float> const &,float,int>::_Do_call+0x24 [C:\Program Files\Microsoft Visual Studio\18\Community\VC\Tools\MSVC\14.50.35717\include\functional @ 885]
(Inline Function) --------`-------- sd_cli!std::_Func_class<sd::Tensor<float>,sd::Tensor<float> const &,float,int>::operator()+0x2a [C:\Program Files\Microsoft Visual Studio\18\Community\VC\Tools\MSVC\14.50.35717\include\functional @ 930]
000000de`2771d730 00007ff6`d23956b4 sd_cli!sample_lcm+0xe3 [D:\llama.cpp\sd.cpp\src\denoiser.hpp @ 1154]
000000de`2771d8e0 00007ff6`d23868e9 sd_cli!sample_k_diffusion+0x944 [D:\llama.cpp\sd.cpp\src\denoiser.hpp @ 1682]
000000de`2771daa0 00007ff6`d23aa510 sd_cli!StableDiffusionGGML::sample+0x4e9 [D:\llama.cpp\sd.cpp\src\stable-diffusion.cpp @ 1784]
000000de`2771e140 00007ff6`d21b23ee sd_cli!generate_image+0x510 [D:\llama.cpp\sd.cpp\src\stable-diffusion.cpp @ 3407]
000000de`2771f160 00007ff6`d26cd778 sd_cli!main+0x16de [D:\llama.cpp\sd.cpp\examples\cli\main.cpp @ 733]
*** ERROR: Symbol file could not be found.  Defaulted to export symbols for C:\WINDOWS\System32\KERNEL32.DLL -
(Inline Function) --------`-------- sd_cli!invoke_main+0x22 [D:\a\_work\1\s\src\vctools\crt\vcstartup\src\startup\exe_common.inl @ 78]
000000de`2771fdb0 00007ffd`9e39e8d7 sd_cli!__scrt_common_main_seh+0x10c [D:\a\_work\1\s\src\vctools\crt\vcstartup\src\startup\exe_common.inl @ 288]
*** ERROR: Symbol file could not be found.  Defaulted to export symbols for ntdll.dll -
000000de`2771fdf0 00007ffd`9f46c3fc KERNEL32!BaseThreadInitThunk+0x17



 - Added proper in-backend handling for GGML_OP_TIMESTEP_EMBEDDING in D:\llama.cpp\sd.cpp\ggml\src\ggml-dx12\ggml-dx12.cpp:
  - dx12_supports_op now returns true for it.
  - At dispatch time, the backend flushes the cmd list, reads src0 via ggml_backend_tensor_get, computes the sin/cos embedding on 
host, writes back via ggml_backend_tensor_set, then resumes GPU recording.
  - Logs a one-time warning per process.

❯ ran successfully but the output image is corrupted.

The bug was that on subsequent denoising steps, the replay cache was skipping the TIMESTEP_EMBEDDING node (default decision
kind = DX12_DEC_SKIP), so all steps after the first reused stale embedding data.

Fix: the handler now runs before any replay-skip checks and marks the decision as DX12_DEC_COMPUTE so it can never be
early-skipped. The CPU compute + upload now executes every graph (i.e., every denoising step), with fresh timestep values.

===============================================

 - DX12 backend integrated into sd.cpp and registered with ggml.
 - Transfer-context mutex fixed multithreaded model-load crash.
 - TIMESTEP_EMBEDDING now handled by an in-backend CPU-host fallback (compute → upload) that runs every step.
 - Output image matches CPU baseline at ~13s vs ~30s.

Key gotcha for future DX12 host-fallback ops: handler must run before the replay-cache DX12_DEC_SKIP check and mark its decision as
DX12_DEC_COMPUTE — otherwise subsequent graph computes silently skip it.

==============================================

● With --offload-to-cpu in sd.cpp:

  What's offloaded: the model weight tensors (params) for every component — text encoders, UNet/diffusion model, VAE, ControlNet,
  PhotoMaker, etc. They live in CPU RAM instead of GPU VRAM.

  How it works at runtime (see GGMLRunner::offload_all_params / offload_partial_params in D:\llama.cpp\sd.cpp\src\ggml_extend.hpp):

   1. At load time, params_backend = CPU, so params_ctx tensors are allocated in a CPU buffer.
   2. Before each compute graph runs:
    - offload_all_params() allocates a GPU-backed runtime_params_buffer, copies all params from CPU → GPU (via 
  ggml_backend_tensor_copy), and swaps tensor buffer/data/extra pointers so the graph sees GPU-resident weights.
    - The graph executes on GPU.
    - If free_params_immediately is set (or partial offload is used), restore_all_params() / restore_partial_params() swaps the 
  pointers back to CPU and frees the GPU copy.

  What's NOT offloaded:

   - Activations / intermediate compute buffers — those live on the runtime (GPU) backend.
   - Inputs (prompt tokens, latents, conditioning tensors).

  Purpose: Reduce peak VRAM. Trade-off: per-graph CPU→GPU copy of weights adds latency, especially for big models.

===============================================

C:\llama.cpp\sd.cpp\build.dxx>bin\RelWithDebInfo\sd-cli.exe -m d:\llama.cpp\models\SD\gguf\LCM_Dreamshaper_v7-f16.gguf -p "eerie treehouse in the wood" --sampling-method lcm --scheduler lcm --steps 5 --cfg-scale 1.0 --seed 63
[INFO ] ggml_extend.hpp:67   - ggml-dx12: Memory architecture: UMA (host-shared, direct write enabled)
[INFO ] ggml_extend.hpp:67   - ggml-dx12: Fused RMS_NORM blobs: using wave=64 variant
[INFO ] ggml_extend.hpp:67   - ggml-dx12: Shader blobs: using wave=64 variant (device wave=64)
[INFO ] ggml_extend.hpp:67   - ggml-dx12: Device 0: DX120 (AMD Radeon(TM) 8060S Graphics, VRAM: 64.9 GB, SM: 6.8, wave: 64, CV: no, WaveMMA: no, dp4a: yes)
[WARN ] ggml_extend.hpp:70   - ggml-dx12: [dx12-os-mem:init-pc] device=DX120 GlobalMemoryStatusEx: TotalPhys=126615.8 MiB AvailPhys=107786.0 MiB MemoryLoad=14% TotalVirtual=134217727.9 MiB AvailVirtual=134213142.2 MiB
[WARN ] ggml_extend.hpp:70   - ggml-dx12: [dx12-os-mem:init-pc] device=DX120 K32GetProcessMemoryInfo: WorkingSet=47.1 MiB PeakWS=47.1 MiB PrivateUsage=36.8 MiB PageFaults=20345
[WARN ] ggml_extend.hpp:70   - ggml-dx12: [dx12-os-mem:init-pc] device=DX120 DXGI LOCAL: Budget=66454.2 MiB CurrentUsage=5.5 MiB AvailableForReservation=33355.1 MiB CurrentReservation=0.0 MiB
[INFO ] ggml_extend.hpp:67   - ggml-dx12: Memory architecture: UMA (host-shared, direct write enabled)
[INFO ] ggml_extend.hpp:67   - ggml-dx12: Fused RMS_NORM blobs: using wave=64 variant
[INFO ] ggml_extend.hpp:67   - ggml-dx12: Shader blobs: using wave=64 variant (device wave=64)
[INFO ] ggml_extend.hpp:67   - ggml-dx12: Device 1: DX121 (AMD Radeon(TM) 8060S Graphics, VRAM: 64.9 GB, SM: 6.8, wave: 64, CV: no, WaveMMA: no, dp4a: yes)
[WARN ] ggml_extend.hpp:70   - ggml-dx12: [dx12-os-mem:init-pc] device=DX121 GlobalMemoryStatusEx: TotalPhys=126615.8 MiB AvailPhys=107765.2 MiB MemoryLoad=14% TotalVirtual=134217727.9 MiB AvailVirtual=134213018.4 MiB
[WARN ] ggml_extend.hpp:70   - ggml-dx12: [dx12-os-mem:init-pc] device=DX121 K32GetProcessMemoryInfo: WorkingSet=67.5 MiB PeakWS=67.5 MiB PrivateUsage=64.4 MiB PageFaults=30703
[WARN ] ggml_extend.hpp:70   - ggml-dx12: [dx12-os-mem:init-pc] device=DX121 DXGI LOCAL: Budget=66454.2 MiB CurrentUsage=10.9 MiB AvailableForReservation=33355.1 MiB CurrentReservation=0.0 MiB
[INFO ] ggml_extend.hpp:67   - ggml-dx12: Found 2 D3D12 device(s)
[INFO ] stable-diffusion.cpp:212  - loading model from 'd:\llama.cpp\models\SD\gguf\LCM_Dreamshaper_v7-f16.gguf'
[INFO ] model.cpp:216  - load d:\llama.cpp\models\SD\gguf\LCM_Dreamshaper_v7-f16.gguf using gguf format
[INFO ] stable-diffusion.cpp:305  - Version: SD 1.x
[INFO ] stable-diffusion.cpp:333  - Weight type stat:                      f32: 703  |     f16: 428
[INFO ] stable-diffusion.cpp:334  - Conditioner weight type stat:          f32: 122  |     f16: 74
[INFO ] stable-diffusion.cpp:335  - Diffusion model weight type stat:      f32: 404  |     f16: 282
[INFO ] stable-diffusion.cpp:336  - VAE weight type stat:                  f32: 176  |     f16: 72
[INFO ] stable-diffusion.cpp:640  - using VAE for encoding / decoding
[INFO ] auto_encoder_kl.hpp:525  - vae decoder: ch = 128
  |==================================================| 1131/1131 - 4.29GB/s
[INFO ] model.cpp:999  - loading tensors completed, taking 0.45s (process: 0.00s, read: 0.33s, memcpy: 0.00s, convert: 0.00s, copy_to_backend: 0.08s)
[INFO ] stable-diffusion.cpp:873  - total params memory size = 1969.78MB (VRAM 1969.78MB, RAM 0.00MB): text_encoders 235.06MB(VRAM), diffusion_model 1640.25MB(VRAM), vae 94.47MB(VRAM), controlnet 0.00MB(VRAM), pmid 0.00MB(VRAM)
[INFO ] stable-diffusion.cpp:931  - running in eps-prediction mode
[INFO ] stable-diffusion.cpp:3367 - generate_image 512x512
[INFO ] denoiser.hpp:539  - get_sigmas with LCM scheduler
[INFO ] stable-diffusion.cpp:2814 - sampling using LCM method
[INFO ] ggml_extend.hpp:67   - ggml-dx12: Auto-tune v9 loaded: Q4_K_dp4a=32t Q5_K_dp4a=32t F16_mr=256t (K>=0 uses 256t)
[INFO ] stable-diffusion.cpp:3168 - get_learned_condition completed, taking 0.02s
[INFO ] stable-diffusion.cpp:3401 - generating image: 1/1 - seed 63
[WARN ] ggml_extend.hpp:70   - ggml-dx12: TIMESTEP_EMBEDDING: no GPU shader, computing on CPU and uploading (per graph)
  |==================================================| 5/5 - 2.04it/s
[INFO ] stable-diffusion.cpp:3432 - sampling completed, taking 2.47s
[INFO ] stable-diffusion.cpp:3452 - generating 1 latent images completed, taking 2.48s
[INFO ] stable-diffusion.cpp:3192 - decoding 1 latents
[INFO ] stable-diffusion.cpp:3208 - latent 1 decoded, taking 1.82s
[INFO ] stable-diffusion.cpp:3212 - decode_first_stage completed, taking 1.82s
[INFO ] stable-diffusion.cpp:3591 - generate_image completed in 4.34s
[INFO ] main.cpp:441  - save result image 0 to 'output.png' (success)
[INFO ] main.cpp:490  - 1/1 images saved

C:\llama.cpp\sd.cpp\build.dxx>output.png

C:\llama.cpp\sd.cpp\build.dxx>

=======================================================

D:\llama.cpp\models\SD>c:\llama.cpp\sd.cpp\build.dxx\bin\RelWithDebInfo\sd-cli.exe -M convert -m d:\llama.cpp\models\SD\LCM_PT -o gguf\LCM_Dreamshaper_v7-Q4_K.gguf  --type q4_K
[INFO ] model.cpp:213  - load d:\llama.cpp\models\SD\LCM_PT using diffusers format
[ERROR] model.cpp:299  - failed to open 'd:\llama.cpp\models\SD\LCM_PT/text_encoder_2/model.safetensors'
[INFO ] convert.cpp:110  - model tensors mem size: 3022.13MB
  |==============================>                   | 686/1130 - 833.24MB/s
  |=========================================>        | 934/1130 - 868.64MB/s
  |==================================================| 1130/1130 - 769.17MB/s
[INFO ] model.cpp:999  - loading tensors completed, taking 5.29s (process: 0.00s, read: 0.42s, memcpy: 0.00s, convert: 3.52s, copy_to_backend: 0.00s)
[INFO ] convert.cpp:75   - load tensors done
[INFO ] gguf_io.cpp:116  - trying to save tensors to gguf\LCM_Dreamshaper_v7-Q4_K.gguf
[INFO ] main.cpp:573  - convert 'd:\llama.cpp\models\SD\LCM_PT'/'' to 'gguf\LCM_Dreamshaper_v7-Q4_K.gguf' success


D:\llama.cpp\models\SD>c:\llama.cpp\sd.cpp\build.dxx\bin\RelWithDebInfo\sd-cli.exe -M convert -m d:\llama.cpp\models\SD\LCM_PT -o gguf\LCM_Dreamshaper_v7-Q8_0.gguf  --type q8_0
[INFO ] model.cpp:213  - load d:\llama.cpp\models\SD\LCM_PT using diffusers format
[ERROR] model.cpp:299  - failed to open 'd:\llama.cpp\models\SD\LCM_PT/text_encoder_2/model.safetensors'
[INFO ] convert.cpp:110  - model tensors mem size: 3073.88MB
  |==============================>                   | 686/1130 - 49.34MB/s
  |=========================================>        | 934/1130 - 49.53MB/s
  |==================================================| 1130/1130 - 49.99MB/s
[INFO ] model.cpp:999  - loading tensors completed, taking 81.36s (process: 0.00s, read: 78.57s, memcpy: 0.00s, convert: 0.07s, copy_to_backend: 0.00s)
[INFO ] convert.cpp:75   - load tensors done
[INFO ] gguf_io.cpp:116  - trying to save tensors to gguf\LCM_Dreamshaper_v7-Q8_0.gguf
[INFO ] main.cpp:573  - convert 'd:\llama.cpp\models\SD\LCM_PT'/'' to 'gguf\LCM_Dreamshaper_v7-Q8_0.gguf' success

