# Build

Base: IllusionMods/HSPlugins commit 9220f2a6b2e6f8e0f62ea9acec6238f5ab6ed1cf, VideoExport 2.1.1.
Apply dynamic-resolution.patch to that checkout; build VideoExport.KKS/VideoExport.KKS.csproj using upstream prerequisites. Source.zip contains the two changed C# files and isolated tests; it is not a standalone project.

The included DLL was compiled from that base plus this patch using Roslyn 4.8 with KKS,BEPINEX,KOIKATSU,SUNSHINE, optimization and deterministic compilation, and the project's listed sources/resources. Local references: BepInEx 5.4.23.5, KKSAPI 1.48.1.0, KKS_Screencap 21.1.4.1 and the installed game's Unity assemblies. A compile-only UnityEngine.UI reference exposed UIBehaviour.OnDisable to match upstream's public override. Game/dependency DLLs are not distributed. Older dependency versions are not tested.

SHA-256 (VideoExport.dll):
7361CD6E649F414701FF558BEA89DED873D2F086C6CF3D833F01E5DA507D93AA

Validation: full compilation; deterministic rebuild; five isolated helper cases; embedded resource comparison; user-confirmed in-game export on 2026-10-28. Extract Source.zip and run tests/Test-CaptureSize.ps1 in a fresh PowerShell 7 process for isolated helper tests with Unity/logger stubs.

Limitations: fixed even-sized RGBA capture only. Header freshness and changing resolution during export are not handled by this patch. Invalid header capacity/channel validation in the frame-copy path remains upstream behavior.

