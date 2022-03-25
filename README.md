# Security margins paper

Repository related to security margins paper contains input configurations and experiment results.
The paper is currently submitted under title "Large-scale randomness study of security margins for more than 100 cryptographic functions"

Main result of our paper is [ftable.txt](https://github.com/ph4r05/SecurityMarginsPaper/blob/main/results-table/ftable.txt?raw=true), processed randomness batteries results for various cryptographic functions. 

## Project Structure
- dir `results-table` contains full analysis result for each run configuration
- dir `results-ref` contains reference run results
- dir `rtt-configs.tar.gz` contains configuration files for CryptoStreams that were used to generate analyzed dataset

## Full dataset
As full testing datasets have more than 20GB it is not possible to host them here. In order to obtain them, please open an issue and we will provide temporary download link.

## Tools
Pls note that current version is anonymized for review.

- RTT
- CryptoStreams
- Randomness Testing Toolkit

### Ftable format

Example of the ftable.txt format. It shows results for MD5 hash function, with input strategy LHW (low hamming weight), for data size 100 MB, rounds 6 to 25.
Rounds [6, 20] are detected as biased ("R"), the rest is not. 

For example round 10 is detected as biased, with 601 tests failing with alpha=1e-5 out of 735 all performed tests, which is 81.8% of tests failing. 
MD5 has maximally 64 rounds, security margin for r10 is 84.38%, all 3 seeds were detected as biased (`111` - bitmap of failed seeds).
Then `exs` shows experiment IDs under which exact detailed results can be found for this particular configuration, `mvp` shows minimal pvalues per seed. 

```
                       H::MD5 |                 hw:104857600 |    6 | R (688/ 735 ~0.936; c R (243/ 245) | hcr:  - , max  64, sm: 90.62 %, sds 111) exs: 303623, 305846, 308990, mpv: [0.000e+00, 0.000e+00, 0.000e+00]
                       H::MD5 |                 hw:104857600 |    7 | R (659/ 735 ~0.897; c R (242/ 245) | hcr:  - , max  64, sm: 89.06 %, sds 111) exs: 303626, 305852, 308996, mpv: [0.000e+00, 0.000e+00, 0.000e+00]
                       H::MD5 |                 hw:104857600 |    8 | R (645/ 735 ~0.878; c R (236/ 245) | hcr:  - , max  64, sm: 87.50 %, sds 111) exs: 303629, 305858, 309002, mpv: [0.000e+00, 0.000e+00, 0.000e+00]
                       H::MD5 |                 hw:104857600 |    9 | R (601/ 735 ~0.818; c R (221/ 245) | hcr:  - , max  64, sm: 85.94 %, sds 111) exs: 303632, 305864, 309008, mpv: [0.000e+00, 0.000e+00, 0.000e+00]
                       H::MD5 |                 hw:104857600 |   10 | R (510/ 735 ~0.694; c R (183/ 245) | hcr:  - , max  64, sm: 84.38 %, sds 111) exs: 303635, 305870, 309014, mpv: [0.000e+00, 0.000e+00, 0.000e+00]
                       H::MD5 |                 hw:104857600 |   11 | R (433/ 735 ~0.589; c R (147/ 245) | hcr:  - , max  64, sm: 82.81 %, sds 111) exs: 303638, 305876, 309020, mpv: [0.000e+00, 0.000e+00, 0.000e+00]
                       H::MD5 |                 hw:104857600 |   12 | R (303/ 735 ~0.412; c R (112/ 245) | hcr:  - , max  64, sm: 81.25 %, sds 111) exs: 303641, 305882, 309026, mpv: [0.000e+00, 0.000e+00, 0.000e+00]
                       H::MD5 |                 hw:104857600 |   13 | R (215/ 735 ~0.293; c R ( 77/ 245) | hcr:  - , max  64, sm: 79.69 %, sds 111) exs: 303644, 305888, 309032, mpv: [1.000e-300, 1.000e-300, 1.000e-300]
                       H::MD5 |                 hw:104857600 |   14 | R ( 47/ 735 ~0.064; c R ( 11/ 245) | hcr:  - , max  64, sm: 78.12 %, sds 111) exs: 303647, 305894, 309038, mpv: [1.000e-300, 1.000e-300, 1.000e-300]
                       H::MD5 |                 hw:104857600 |   15 | R ( 27/ 735 ~0.037; c R ( 11/ 245) | hcr:  - , max  64, sm: 76.56 %, sds 111) exs: 303650, 305900, 309044, mpv: [1.000e-300, 1.000e-300, 1.000e-300]
                       H::MD5 |                 hw:104857600 |   16 | R (  9/ 735 ~0.012; c R (  4/ 245) | hcr:  - , max  64, sm: 75.00 %, sds 111) exs: 303653, 305906, 309050, mpv: [8.800e-191, 1.000e-300, 1.000e-300], [453, 510, 515; 453, 510, 515; 453, 510, 515]
                       H::MD5 |                 hw:104857600 |   17 | R (  7/ 735 ~0.010; c R (  4/ 245) | hcr:  - , max  64, sm: 73.44 %, sds 111) exs: 303656, 305912, 309056, mpv: [7.100e-44, 1.100e-94, 1.000e-300], [453, 515; 453, 515; 453, 510, 515]
                       H::MD5 |                 hw:104857600 |   18 | R (  6/ 735 ~0.008; c R (  3/ 245) | hcr:  - , max  64, sm: 71.88 %, sds 111) exs: 314404, 314583, 314809, mpv: [2.400e-19, 1.800e-26, 3.300e-41], [453, 515; 453, 515; 453, 515]
                       H::MD5 |                 hw:104857600 |   19 | R (  6/ 735 ~0.008; c R (  3/ 245) | hcr:  - , max  64, sm: 70.31 %, sds 111) exs: 314405, 314584, 314810, mpv: [2.400e-19, 2.400e-19, 2.400e-19], [453, 515; 453, 515; 453, 515]
                       H::MD5 |                 hw:104857600 |   20 | R (  3/ 735 ~0.004; c R (  3/ 245) | hcr:  - , max  64, sm: 68.75 %, sds 111) exs: 314406, 314585, 314811, mpv: [1.600e-14, 1.600e-14, 1.600e-14], [453; 453; 453]
                       H::MD5 |                 hw:104857600 |   21 | - (  2/ 735 ~0.003; c - (  1/ 245) | hcr:  - , max  64, sds 001) exs: 316823, 316832, 316841, mpv: [1.000e-09, 7.314e-04, 2.500e-13], [453; ; 453]
                       H::MD5 |                 hw:104857600 |   22 | - (  0/ 735 ~0.000; c - (  0/ 245) | hcr:  - , max  64, sds 000) exs: 316824, 316833, 316842, mpv: [4.609e-03, 4.381e-03, 5.026e-03], [; ; ]
                       H::MD5 |                 hw:104857600 |   23 | - (  1/ 735 ~0.001; c - (  1/ 245) | hcr:  - , max  64, sds 000) exs: 316825, 316834, 316843, mpv: [5.281e-03, 3.800e-03, 2.800e-06], [; ; 448]
                       H::MD5 |                 hw:104857600 |   24 | - (  0/ 735 ~0.000; c - (  0/ 245) | hcr:  - , max  64, sds 000) exs: 381849, 381850, 381851, mpv: [4.587e-03, 3.600e-03, 2.035e-05], [; ; ]
                       H::MD5 |                 hw:104857600 |   25 | - (  0/ 735 ~0.000; c - (  0/ 245) | hcr:  - , max  64, sds 000) exs: 381852, 381853, 381854, mpv: [4.838e-04, 2.635e-05, 1.780e-04], [; ; ]
```
