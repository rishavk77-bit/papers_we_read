# MMAudio: Taming Multimodal Joint Training for High-Quality Video-to-Audio Synthesis

Ho Kei Cheng, Masato Ishii , Akio Hayakawa,Takashi Shibuya,Alexander Schwing **NeurIPS** **2024**

## Summary

The paper is about generation of high quality semantically aligned audio samples . The core idea is simple but powerful - instead of only learning from limited video-audio pairs (which are hard to collect at large level), the model jointly train on both video-audio and text-audio data. Additionally , synchrony b/w audio video is improved by conditional synchronization module that aligns video conditions with audio latents at the frame level. Their model also performed very well on simple text to audio genration showing joint training does not hinder single modality performance.

## Contributions

- Multimodal Joint Training Paradigm.
- Conditional Synchronization Module.
- Aligned RoPE Positional Embeddings.
- Competitive Text-to-Audio Generation.

## Method
MMAudio generates audio using flow based model using multimodal conditioning . The approach combines three key components: a multimodal transformer architecture, a conditional synchronization module, and a joint training strategy.
1. Conditional Flow Matching Framework.
2. Multimodal Transformer Architecture.
   Key components :

     a. RoPE based positional encoding.
     b. Concatenation of Q,K,V for joint attention then splitting the modalities .

3. Conditional Synchronization module : Pipeline looks like - Extracting high frame rate visual features then project and upsample to match audio rate thus applying token level conditioing.
   
<img width="853" height="522" alt="Screenshot 2025-09-30 at 4 02 48 AM" src="https://github.com/user-attachments/assets/9b15c2f1-8b03-425f-bf43-43fbc3c56299" />

## Results

<img width="799" height="382" alt="Screenshot 2025-09-30 at 4 10 50 AM" src="https://github.com/user-attachments/assets/e7796fbb-6839-4f2f-ad15-03604de59b92" />

MMAudio achieves state-of-the-art performance across all metrics among public models, with the smallest model (S-16kHz, 157M params) outperforming significantly larger baselines.


## Two-Cents

The model had exceptional synchronisation will SOTA on video to audio . But what i felt is that "joint training" is oversold . we can see in ablation study that this what not revolutionary under the hood . 
Other limitation they talked is about generating the intelligible sounds as human sounds are more complex and their model aimed at Foley may fail to accomodate .

## Resources

<https://arxiv.org/abs/2412.15322>
