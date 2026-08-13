# ishAD Windows Evaluation Release

Bu paket, ishAD'nin gerçek Active Directory ortamında kontrollü değerlendirilmesi
için hazırlanmıştır.

## Paket

- `dist/win-x64/ishAD.exe` — publish sonrası gerçek self-contained binary
- `installer/ishAD.iss` — Inno Setup installer tanımı
- `config/evaluation.json` — güvenli değerlendirme ayarları
- `docs/FIRM-EVALUATION-GUIDE.md` — firma test kılavuzu
- `docs/TEST-MATRIX.md` — test matrisi
- `build/Publish-Windows.ps1` — Windows publish scripti

## Binary hakkında

Bu çalışma ortamında .NET SDK bulunmadığı için burada sahte bir `ishAD.exe`
üretilmemiştir. `Publish-Windows.ps1`, Windows + .NET 8 SDK üzerinde gerçek
self-contained `win-x64` binary üretir.

## Publish

PowerShell:

    Set-ExecutionPolicy -Scope Process Bypass
    .\build\Publish-Windows.ps1

Ardından `dist\win-x64\ishAD.exe` oluşur.

Installer için Inno Setup kuruluysa:

    iscc.exe installer\ishAD.iss

Installer:

    dist\installer\ishAD-Windows-Evaluation-Setup.exe
