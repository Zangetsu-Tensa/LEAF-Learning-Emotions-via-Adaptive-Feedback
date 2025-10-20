# 🎮 PPO-Breakout — Proximal Policy Optimization from Scratch for Atari Environments

> _"Learning to play like a human — one clipped gradient at a time."_  

This repository implements **Proximal Policy Optimization (PPO)** entirely **from scratch** in **PyTorch**, trained on **Atari Breakout (NoFrameskip-v4)** with frame-stacking, grayscale preprocessing, and parallel actor environments.  

It’s built for clarity and depth — every part of PPO is explicitly implemented and optimized for understanding, not just performance.

---

## 🧠 Overview

**Proximal Policy Optimization (PPO)** is one of the most stable and widely used reinforcement learning algorithms introduced by **OpenAI** (Schulman et al., 2017).  
This implementation captures the core ideas behind PPO — including **clipped policy objectives**, **advantage estimation (GAE)**, and **actor-critic training**, all without relying on external RL libraries.

---

## 🚀 Key Features

- 🧩 **From-Scratch PPO Implementation** — no Stable Baselines or RLlib dependencies  
- ⚙️ **Actor–Critic CNN Architecture** for visual Atari environments  
- 🌀 **Parallelized Multi-Actor Setup** for efficient experience collection  
- 🎚️ **Generalized Advantage Estimation (GAE)** for stable gradient updates  
- 🔒 **Clipped Surrogate Objective** for reliable policy improvement  
- 📉 **Value Function Clipping** (from PPO2 improvements, 2020)  
- 📈 **Auto LR Scheduling & Reward Plotting**  

---

## 🏗️ Architecture Overview

┌──────────────────────────────────────────────────┐
│ ENVIRONMENT │
│ (BreakoutNoFrameskip-v4, FrameStacked 4x) │
└──────────────────────────────────────────────────┘
│
▼
Convolutional Encoder
│
▼
┌──────────────────┐
│ Shared Feature h │
└──────────────────┘
│ │
▼ ▼
Actor (π) Critic (V)
│ │
▼ ▼
Action State Value