# Mobile 1-D Face Liveness Detection Dataset

The dataset was created with the goal of evaluating models for **liveness detection on the fly, based on photoplethysmography (rPPG) estimated pulses**.  It simulates a setting where a liveness verification step is conducted during an user authentication phase in a mobile phone. To keep the application responsive, liveness needs to be detected on an atmost 5s video, in a non-intrusive manner.

For more details and dataset statistics, please refer to our paper: **[Temporal Convolutional Networks for Robust Face Liveness Detection](https://link.springer.com/chapter/10.1007/978-3-031-04881-4_21)**
*, R. Padnevych, D. Carmo, D. Semedo, J. Magalhães, Proceedings of the 10th  10th Iberian Conference on Pattern Recognition and Image Analysis (ibPRIA),  2022. (Full paper)*

# Dataset download

The dataset can be downloaded [here](https://drive.google.com/file/d/1ZhL-2zVgqh9J49IRTKiDg-HCoBac2fgQ/view?usp=sharing). 

# Dataset Structure and Sample Format

The dataset zip file is structured in two folders, each corresponding to a class:
 * Real - Samples belonging to the "Real" class, i.e. genuine pulses. 
 * Fake - Samples belonging to the "Fake" class, i.e. pulses corresponding to presentation attacks.

Each sample csv is structured as `output_<First Frame Instant>-<Last Frame Instant>_000.mp4 (<Video id>).csv`. For example, the file `output_004-009_000.mp4 (32).csv` denotes a pulse sample extracted from video 33, starting at second 4 and ending at second 9.


Each sample (.csv file) line (corresponding to an instant t) has the following properties:
 - **Timestamp** - Relative sample timestamp t;
 - **BPM** - Estimated Beats Per Minute;
 - **Signal stable?** - Flag that indicates if the signal is stable  
 - **Valid pulse?** - Flag that indicates if the pulse is valid;
 - **Number of peaks** - Number of peaks in the signal;
 - **Nr. peaks > 2** - Flag that indicates if the Number of Peaks is > 2;
 - **Peaks between 40-240 bpm?** - Flag that indicates if the peaks correspond to a bpm in the inveral 40-240;
 - **avg(peak amplitudes)** - Average peak amplitudes;
 - **s(peak amplitudes)** - Standard deviation of peak amplitues;
 - **s(peak amplitudes) < 0.5?** - Flag that indicates if standard deviation of peak amplitues is lower than 0.5;
 - **All peak amplitudes > 60?** - Flag that indicates if all peak amplitues are greater than 60;
 - **s(peak distances)** - Standard deviation of peak distances;
 - **s(peak distances) < 0.5?**- Flag that indicates if the standard deviation of peak distances is lower than 0.5;
 - **Raw signal** - Raw value of the signal;
 - **Pulse signal** - Pulse signal value.


## Reference

If you found this dataset useful, please cite the following paper:

    @InProceedings{10.1007/978-3-031-04881-4_21,
       author="Padnevych, Ruslan
          and Carmo, David
          and Semedo, David
          and Magalh{\~a}es, Jo{\~a}o",
          editor="Pinho, Armando J.
          and Georgieva, Petia
          and Teixeira, Lu{\'i}s F.
          and S{\'a}nchez, Joan Andreu",
       title="Temporal Convolutional Networks for Robust Face Liveness Detection",
       booktitle="Pattern Recognition and Image Analysis",
       year="2022",
       publisher="Springer International Publishing",
       address="Cham",
       pages="255--267",
       isbn="978-3-031-04881-4"
     }


## License

[Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)
