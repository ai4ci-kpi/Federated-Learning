class: middle, center, title-slide

# Distributed and Federated Learning

## Federated learning for healthcare data

<br><br>
Yuri Gordienko<br>
Ivan Zhuk<br>
Yuriy Kochura<br>

---

# Us

This material is presented by:
- Theoretical lecture: .bold[Yuri Gordienko]
- Exercise session: .bold[Ivan Zhuk] and .bold[Yuriy Kochura]


Feel free to contact .bold[Yuriy Kochura] at [iuriy.kochura@gmail.com](mailto:iuriy.kochura@gmail.com) or on Telegram &mdash; <a href="https://t.me/y_kochura">@y_kochura</a> for assistance.

<br>

.grid[
.kol-1-3[
.circle.center.width-70[![](figures/lec1/Yuri-Gordienko.jpg)]
.bold.center[Yuri Gordienko]
]

.kol-1-3[ 
.circle.center.width-70[![](figures/lec1/Ivan-Zhuk_photo.png)]
.bold.center[Ivan Zhuk]
  ]


.kol-1-3[ 
.circle.center.width-65[![](figures/lec1/ykochura.jpg)]
.bold.center[Yuriy Kochura]

]]

---


class:  black-slide, middle 
background-image: url(./figures/lec1/1726464736780.png)
background-size: cover


# Agenda

.larger-x[ <p class="shadow" style="line-height: 200%;"> 

🎙️ AI in Healthcare <br>
🎙️ Market Size & Trends <br> 
🎙️  <br> 

</p>]

---


class: blue-slide, middle, center
count: false

.larger-xxx[AI in Healthcare]

---

class:  middle

# AI in medicine

.width-100[![](/figures/lec1/ai-in-medicine.png)]

<br><br>

 
<table style="width:500px; table-layout: fixed; border: 1px solid #000;">
  <thead>
    <tr>
      <th style="width: 100px;">Year</th>
      <th style="width: 200px;">FDA-Approved AI Tools</th>
      <th style="width: 200px;">Global Investment (USD)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>2021</td>
      <td>~128</td>
      <td>~$7B</td>
    </tr>
    <tr>
      <td>2024</td>
      <td>~169</td>
      <td>~$26.57B</td>
    </tr>
  </tbody>
</table>

.footnote[Credit: [Artificial Intelligence and Machine Learning (AI/ML)-Enabled Medical Devices](https://www.fda.gov/medical-devices/software-medical-device-samd/artificial-intelligence-and-machine-learning-aiml-enabled-medical-devices). Nicola Rieke and Yuhong Wen - FEDERATED LEARNING FOR MEDICAL IMAGING.]

---

background-image: url(./figures/lec1/building-blocks.png)
background-size: contain


# From research ...
.center[## Improving state of the art performance in controlled settings]

.footnote[Credit: Nicola Rieke and Yuhong Wen - FEDERATED LEARNING FOR MEDICAL IMAGING.]

---

background-image: url(./figures/lec1/app-in-medicine.png)
background-size: contain


#  ... to applications
.center[## Achieving human-level performance on large data and clinical settings]

.footnote[Credit: Nicola Rieke and Yuhong Wen - FEDERATED LEARNING FOR MEDICAL IMAGING.]

---

class: middle, black-slide, center

<iframe width="600" height="450" src="https://www.youtube.com/embed/AbdVsi1VjQY" frameborder="0" allowfullscreen></iframe>

How AI is advancing medicine (Google, 2018)

---

class: middle,

.center.width-50[![](./figures/lec1/medpalm.gif)]

.center[Med-PaLM 2 (Google) is a large language model tuned for the medical domain. It reaches 85%+ accuracy on the MedQA medical exam benchmark in research.]

.footnote[Credit: Google Research, [Med-PaLM](https://sites.research.google/med-palm/), 2022.]

???
What makes these AI systems really different is that they offer a new interface. AI is no longer embedded in tools but in direct contact with us, humans.

For example, Med-PaLM 2 is a large language model tuned for the medical domain. It can be interacted with using natural language, as if you were talking to a medical expert. You do not need to know how to write code or how to define these mathematical models. You just ask a question, and it will give you an answer.

---


class: middle

## AlphaFold: From a sequence of amino acids to a 3D structure

.grid[
.kol-2-3.center.width-100[![](./figures/lec1/alphafold-nature.png)]
.kol-1-3.center.width-80[![](./figures/lec1/alphafold-prediction.gif)]
.kol-1-3.circle.center.width-80[![](./figures/lec1/John_Jumper,_2024_Nobel_Prize_Laureate_in_Chemistry.jpg) 
.smaller-x[[John Jumper](https://en.wikipedia.org/wiki/John_M._Jumper)] <br>
.smaller-xx[(The 2024 Nobel Prize in Chemistry)]]
.kol-1-4.circle.center.width-40[![](./figures/lec1/Nobel_Prize.png) ]

]

???

AlphaFold is a neural network based on the trasnformer architecture that can predict the 3D structure of a protein from its amino acid sequence.

This problem is important because the 3D structure of a protein determines its function, and understanding protein function is key to understanding biology and designing new drugs.

However, determining the 3D structure of a protein experimentally is difficult and expensive, taking up to months just to solve a single structure.

AlphaFold has been a breakthrough in this area, and has been able to predict the 3D structure of proteins with high accuracy, in just a couple of minutes for the longest sequences.

---

class: middle, black-slide, center

<iframe width="600" height="450" src="https://www.youtube.com/embed/gg7WjuFs8F4" frameborder="0" allowfullscreen></iframe>

AI for Science (Deepmind, AlphaFold, 2020)

---

class: middle

## Drug discovery with graph neural networks

.center.width-80[![](./figures/lec1/cell.png)]

???

A second example is the use of graph neural networks to discover new drugs.

Discovering new drugs is a complex and expensive search problem, where the goal is to find molecules that will bind to a target protein and modulate its function. Unfortunately, this problem is difficult for two reasons:

  - first, the search space is huge -- the space all possible pharmacologically active molecules is estimated to be in the order of 10^60 molecules.
  - second, the binding of a molecule to a protein is a complex process that is difficult to model. Laboratory experiments are necessary to evaluate the binding of a molecule to a protein, and these experiments are expensive and time-consuming.

Graph neural networks have been a breakthrough in this area, and have been able to predict the properties of molecules with high accuracy.

In a sense, they can serve as a virtual laboratory that can be used to pre-screen millions of molecules in a matter of hours, thereby reducing the laboratory work to only the most promising candidates.

---

class: blue-slide, middle, center
count: false

.larger-xxx[Market Size & Trends]

---

class: black-slide, middle

<!-- background-image: url(./figures/lec1/ai-healthcare-market.png)
background-size: contain -->

.width-100[![](/figures/lec1/ai-healthcare-market.png)]

.smaller-xx[.bold[CAGR] (Compound Annual Growth Rate)]

.alert[A .bold[key factor] driving market growth is the increasing demand in the healthcare sector for enhanced efficiency, accuracy, and better patient outcomes.]

.footnote[Credit: [AI In Healthcare Market Size, Share, And Trends Analysis Report By Component (Hardware, Services), By Application, By End Use, By Technology, By Region (North America, Europe, APAC, Latin America, MEA), And Segment Forecasts, 2025 - 2030](https://www.grandviewresearch.com/industry-analysis/artificial-intelligence-ai-healthcare-market).]

---

class: black-slide, middle

.width-100[![](/figures/lec1/ai-healthcare-market-share.png)]

.alert.smaller-x[The .bold[context-aware computing] segment is expected to grow at the fastest CAGR between 2025 and 2030. AI algorithms integrate and analyze diverse data sources such as electronic health records (EHRs), real-time vital signs, medical history, environmental factors, and patient activity to understand patient context dynamically.]

.footnote[Credit: [AI In Healthcare Market Size, Share, And Trends Analysis Report By Component (Hardware, Services), By Application, By End Use, By Technology, By Region (North America, Europe, APAC, Latin America, MEA), And Segment Forecasts, 2025 - 2030](https://www.grandviewresearch.com/industry-analysis/artificial-intelligence-ai-healthcare-market).]

---

class: black-slide, middle

.width-100[![](/figures/lec1/ai-healthcare-industry-dynamics.png)]

.alert.smaller-x[The Healthcare AI market exhibits a high degree of innovation, characterized by ongoing advancements in technology. Rapid developments in machine learning, deep learning, natural language processing, and computer vision are driving the evolution of AI-powered healthcare solutions.]

.footnote[Credit: [AI In Healthcare Market Size, Share, And Trends Analysis Report By Component (Hardware, Services), By Application, By End Use, By Technology, By Region (North America, Europe, APAC, Latin America, MEA), And Segment Forecasts, 2025 - 2030](https://www.grandviewresearch.com/industry-analysis/artificial-intelligence-ai-healthcare-market).]

---

class: black-slide, middle

.width-100[![](/figures/lec1/ai-healthcare-market-trends-by-region.png)]

.alert.smaller-x[North America AI in healthcare industry dominated the global market and accounted for the largest revenue share of over 54% in 2024. 

AI in healthcare industry in the UK held the largest market share in the European region in 2024.]

.footnote[Credit: [AI In Healthcare Market Size, Share, And Trends Analysis Report By Component (Hardware, Services), By Application, By End Use, By Technology, By Region (North America, Europe, APAC, Latin America, MEA), And Segment Forecasts, 2025 - 2030](https://www.grandviewresearch.com/industry-analysis/artificial-intelligence-ai-healthcare-market).]

---

class: middle

# Key Companies

The following are the .bold[leading companies] in the AI in healthcare market. These companies collectively hold the largest market share and dictate industry trends:

.grid[
.kol-1-2[
- Microsoft
- IBM
- Google
- NVIDIA Corporation
- Intel Corporation
- Itrex Group]
.kol-1-2[
- GE Healthcare
- Medtronic
- Oracle
- Medidata
- Merck
- IQVIA
]]

.footnote[Credit: [AI In Healthcare Market Size, Share, And Trends Analysis Report By Component (Hardware, Services), By Application, By End Use, By Technology, By Region (North America, Europe, APAC, Latin America, MEA), And Segment Forecasts, 2025 - 2030](https://www.grandviewresearch.com/industry-analysis/artificial-intelligence-ai-healthcare-market).]

---



background-image: url(./figures/lec1/application.png)
background-size: contain

# Application framework

.footnote[Credit: Nicola Rieke | Sr. Deep Learning Solution Architect - Healthcare - FEDERATED LEARNING USING CLARA TRAIN.]

---


class: end-slide, center
count: false

.larger-xxxx[🏁]


