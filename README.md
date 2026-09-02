# Monitor-Power-Supply-With-LCD-1602
# PSU Monitor (INA226 + Arduino Nano + LCD 16x2 I2C)

Monitor tegangan, arus, daya, dan akumulasi charge (mAh/Ah) untuk PSU service bench.

## Fitur
- Tampilan real-time: **V, A, W, mAh/Ah**
- Auto range charge:
  - `< 1.000 Ah` tampil mAh
  - `>= 1.000 Ah` tampil Ah
- Tombol 1x:
  - **Short press**: HOLD ON/OFF
  - **Long press**: ZERO current + reset charge
- Anti-flicker display (partial redraw)

## Hardware
- Arduino Nano (ATmega328P)
- INA226 current sensor module (I2C address default `0x44`)
- LCD 16x2 I2C (umum `0x27`)
- Shunt resistor rekomendasi: **5 mΩ, 3W/5W, 1%** (wire/manganin)

## Pinout Singkat
- I2C SDA: A4
- I2C SCL: A5
- Button: D3 ke GND (INPUT_PULLUP)
- Semua GND disatukan

Detail lihat: `docs/pinout.md` dan `docs/wiring.md`.

## Firmware
File utama:
`firmware/nano_ina226_psu_service_final_v5_dot_ok_low_flicker.ino`

Parameter penting:
- `SHUNT_OHM`
- `V_OFFSET`
- `I_OFFSET`
- `ALPHA_V`, `ALPHA_I`

## Kalibrasi
Gunakan template:
- `calibration/calibration_log.csv`
- `calibration/test_report_template.md`

Disarankan kalibrasi 2 titik arus (mis. 2A dan 8A) + verifikasi tegangan.

## Produksi
- Checklist perakitan: `production/checklist_assembly.md`
- Checklist QC: `production/checklist_qc.md`
- Registry serial number: `production/serial_number_registry.csv`

## Versioning
Gunakan SemVer:
- `vMAJOR.MINOR.PATCH`
- Contoh: `v1.0.0`

## Changelog
Lihat `CHANGELOG.md`
