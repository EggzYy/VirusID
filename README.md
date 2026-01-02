# VirusID
Identify Pathogens with Native Flouresence Signals and CBAM-STA CRNN

Introduction:

Regardless of the COVID-19 pandemic that reshaped both lives and industries, there has always been a strong interest in developing measurement tools suitable for rapid, reliable, and low-cost analyses for diagnostic purposes.
Sensing and biosensing face this issue by exploiting knowledge and technologies from different topics. It is extremely important to develop procedures that allow both good limits of detection (LOD) and high sensitivity while preserving its attitude to recognize specific molecules (1).
Biomolecular fingerprinting methods via electromagnetic spectrum signals are among the numerous approaches to sensing and biosensing applications.  These methods can yield critical information on molecular structure for physical, chemical, and biological sciences. Despite decades of interest and effort, most portion of the electromagnetic spectrum remains challenging to cover with conventional technologies (2-6).
Biomolecular fingerprinting methods via electromagnetic spectrum signals are also called vibrational spectroscopy. Vibrational spectroscopy contains numerous different methods e.g. Raman Spectroscopy, Surface Enhanced Raman Spectroscopy, Absorption/Transmission Spectroscopy, Fluorescence Spectroscopy, Radioscopy, TeraHertz Spectroscopy, NIR/SWIR/IR Spectroscopy, X-ray spectroscopy, Hysteresisgraphy, Laser-Induced Fluorescence, LED induced fluorescence, Flame Spectroscopy, Absorption Transmission Excitation Emission Matrix, Extremely Low-frequency Electromagnetic Field spectroscopy, Flow cytometry,  Attenuated total reflectance and lots of others. All vibrational spectroscopy techniques are based on the same phenomena related to absorption, excitation, and emission of biomolecules. Briefly, by irradiating the sample with electromagnetic energy, some molecules absorb and re-emit less energetic radiation. This phenomenon is called irradiance, and the spectrum emitted is a function of the specific molecules compounding the microorganisms/viruses (7,8). Some vibrational spectroscopy techniques have already been used for the classification of bacteria (9-16), and viruses (17-22) and even proposed for COVID-19 (23). Vibrational spectroscopy could be a proper approach to developing an instrument suitable for analyzing and classifying viruses. Due to their molecular composition, different proteins, mAbs, antibodies, peptides, etc. emit dissimilar spectra as a fingerprint, allowing their classification. Moreover, the evaluation of the sample concentration could be performed due to the correlation of this parameter with the irradiance intensity.
Although Vibrational spectroscopy methods and kits are very favorable for qualitative and quantitative analyses of protein and peptide-based compounds, there are no solutions in the market using this technology to measure a targeted antibody/protein in plasma/saliva-like complex liquids with a simple spectrometry device which will mostly eliminate consumable and measurement time needs, and speeds up the development of vital projects which are racing against time to save lives. 
One of the reasons for this problem regarding the commercialization of vibrational spectroscopy is the processing of spectral data measured from the complex nature of biological fluids. Noise ratio is a big bottleneck of vibrational spectroscopy. Hence, most of the researchers working on developing virus/microorganism/biochemical specific enhancers/ligands/labels or pre-processing methods to eliminate noise. These approaches are effective; however, they lead to limitations on the necessity of skilled labor, measurement cost, and duration.  
The A.I.-based solution for marker signal detection/processing eliminates biochemical additives (kits) and specialized personnel. Moreover, such a system, in theory, can be used for any biochemical response to the incoming vibrational signals.



Necessary Files to train:
20210329_test.csv: 
https://drive.google.com/file/d/1hiqb2zbdCbWXjRQb-bcKrkO2wbYPyFjx/view?usp=sharing
20210329_train.csv
https://drive.google.com/file/d/1HLpzDwT_mifkQ6pYQBc3tJqCdoLR6yUg/view?usp=sharing

Treshold optimization output:
training_FANFAN_3.csv
https://drive.google.com/file/d/1-1_UAzkiagMmHk_r9Zugunv8-Rw1xbM_/view?usp=sharing

Training Outputs:
best_model_file_FANFAN_3.keras
https://drive.google.com/file/d/1-pupP9vweK42Q73cVDRtm5AkKsfFDapw/view?usp=sharing
cbam_trial_FANFAN_3.keras
https://drive.google.com/file/d/1-JBPNIDqRIyTKmf41HnR9zc1QGaS3Vyo/view?usp=sharing
cbam_trial_FANFAN_3.h5
https://drive.google.com/file/d/1-JN3976FcDlyNYtBthkyvsjrOz04PJA0/view?usp=sharing

Another Model to Ensamble with the Trained Model to increase Generalization:
cbam_trial_FANFAN_2.keras
https://drive.google.com/file/d/1--Xw9u9AYK56-GwhFXw6xTr0LmxNxp7M/view?usp=sharing

Output Ensemble Model:
ensemble_model_fan.keras
https://drive.google.com/file/d/1-1CyH-rsmKuJ6sXMKaTSq1HO2Djzvk0a/view?usp=sharing

References:
1. Jung Y, Jeong JY, Chung BH. Recent advances in immobilization methods of antibodies on solid supports. Analyst. 2008;133(6):697-701. doi:10.1039/b800014j
2. Henry Timmers, Abijith Kowligy, Alex Lind, Flavio C. Cruz, Nima Nader, Myles Silfies, Gabriel Ycas, Thomas K. Allison, Peter G. Schunemann, Scott B. Papp, and Scott A. Diddams, "Molecular fingerprinting with bright, broadband infrared frequency combs," Optica 5, 727-732 (2018)
3. Kendall C, Isabelle M, Bazant-Hegemark F, et al. Vibrational spectroscopy: a clinical tool for cancer diagnostics. The Analyst. 2009 Jun;134(6):1029-1045. DOI: 10.1039/b822130h.
4. Kendall C, Hutchings J, Barr H, Shepherd N, Stone N. Exploiting the diagnostic potential of biomolecular fingerprinting with vibrational spectroscopy. Faraday Discuss. 2011;149:279-356. doi:10.1039/c005379a
5. Sudarson Sekhar Sinha, Stacy Jones, Avijit Pramanik, and Paresh Chandra Ray. Nanoarchitecture Based SERS for Biomolecular Fingerprinting and Label-Free Disease Markers Diagnosis. Accounts of Chemical Research 2016 49 (12), 2725-2735 DOI: 10.1021/acs.accounts.6b00384
6. KOTARO H., TAKURO I., YUSUKE Y., SANGWOOK L., YIZHI L., KAZUKI H., TAKURO I., MISA H., JEE-WOONG P., YUSUKE K., SHINYA S., TAKESHI H., FUMIHITO A., YU H., KEISUKE G. High-throughput label-free molecular fingerprinting flow cytometry. Science Advances.  16 Jan 2019: Vol. 5, no. 1, eaau0241 DOI: 10.1126/sciadv.aau0241
7. Hill, S. C. et al. Real-Time Measurement of Fluorescence Spectra from Single Airborne Biological Particles. Field Analytical Chemistry and Technology 3(4–5), 221–239 (1999).
8. Lakowicz, J. R. Principles of Fluorescence Spectroscopy, Singapore: Springer (2006).
9. Duschek, F. et al. Standoff detection and classification of bacteria by multispectral laser-induced fluorescence. Adv. Opt. Techn. 6(2), 75–83 (2017).
10. Fischbach, T. et al. Standoff detection and classification procedure for bioorganic compounds by hyperspectral laser-induced fluorescence. In Proc. of SPIE, Baltimore (2015).
11. Gebert, F. et al. Novel standoff detection system for the classification of chemical and biological hazardous substances combining temporal and spectral laser-induced fluorescence techniques. The European Physical Journal Plus 133, 169 (2018).
12. Gelfusa, M. et al. A Support Vector Machine Approach to the automatic identification of fluorescence spectra emitted by biological agents. In Proceedings of SPIE. 9995 (2016).
13. Hausmann, A. et al. Standoff detection: classification of biological aerosols using laser-induced fluorescence (LIF) technique. In Proceedings of SPIE (2015).
14. Kraus, M. et al. Classification of Substances Combining Standoff Laser-Induced Fluorescence and Machine Learning. J. Light Laser Curr. Trends 1(003) (2018).
15. Kraus, M. et al. Comparison of Classification Methods for Spectral Data of Laser-induced Fluorescence. Enhancing CBRNE Safety & Security: Proceedings of the SICC 2017 Conference, pp. 49–57 (2018).
16. Joshi, D., Kumar, D., Maini, A. K. & Sharma, R. C. Detection of biological warfare agents using ultra violet-laser induced fluorescence LIDAR. Spectrochimica Acta Part A: Molecular and Biomolecular Spectroscopy 112, 446–456 (2013).
17. Ewan W Blanch, Iain H McColl, Lutz Hecht, Kurt Nielsen, Laurence D Barron. Structural characterization of proteins and viruses using Raman optical activity. Vibrational Spectroscopy, Volume 35, Issues 1–2, 2004, Pages 87-92, ISSN 0924-2031, https://doi.org/10.1016/j.vibspec.2003.12.005.
18. Ewan W Blanch, Lutz Hecht, Laurence D Barron, Vibrational Raman optical activity of proteins, nucleic acids, and viruses. Methods, Volume 29, Issue 2, 2003, Pages 196-209, ISSN 1046-2023, https://doi.org/10.1016/S1046-2023(02)00310-9. 
19. Connor G. Bischak, Sonia Longhi, David M. Snead, Stéphanie Costanzo, Elodie Terrer, Casey H. Londergan. Probing Structural Transitions in the Intrinsically Disordered C-Terminal Domain of the Measles Virus Nucleoprotein by Vibrational Spectroscopy of Cyanylated Cysteines. Biophysical Journal, Volume 99, Issue 5, 2010, Pages 1676-1683, ISSN 0006-3495, https://doi.org/10.1016/j.bpj.2010.06.060. 
20. Cialla, D., Deckert‐Gaudig, T., Budich, C., Laue, M., Möller, R., Naumann, D., Deckert, V., and Popp, J. (2009), Raman to the limit: tip‐enhanced Raman spectroscopic investigations of a single tobacco mosaic virus. J. Raman Spectrosc., 40: 240-243. doi:10.1002/jrs.2123
21. Barron, Laurence D. et al. ‘Structure and Behaviour of Proteins, Nucleic Acids and Viruses from Vibrational Raman Optical Activity. 1 Jan. 2003: 101 – 126. Print.
22. Balandin, Alexander A. and Fonoberov, Vladimir A. Vibrational Modes of Nano-Template Viruses. Journal of Biomedical Nanotechnology. 2005;1:90-95. doi:10.1166/jbn.2005.005 

