# Signals

Dependencies:
- Out depends on Sum. Need 2 blocks in sum so that Out never lacks a sample.
- Sum depends on Dry, Reverb and Delay
- Dry depends on Voices
- Reverb depends on Voices
- Delay depends on Voices
- Voices depend on Sample Blocks (number depends on the maximum playback speed)

Just-in-time processing:
- When Sum has less than 2 blocks, it will copy a block from Dry/Reverb/Delay 
- When Dry/Reverb/Delay has its block copied, it will process the voices
- When the voices have their blocks processed, they will process the Sample Blocks
- When the sample blocks are processed, they will request more from storage

6 Blocks of Delay
- 24 ms of delay
- 4ms per block
- 90 samples per block @22.5kHz
- 192 samples per block @48kHz