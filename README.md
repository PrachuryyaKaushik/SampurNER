# SampurNER: Fine-grained Named Entity Recognition for all 22 scheduled Indian Languages

## Abstract

We introduce **SampurNER**, a fine-grained named entity recognition (FgNER) dataset encompassing **all 22 scheduled Indian languages** spoken by more than **two billion people**. To address the scarcity of FgNER resources for Indian languages, we propose the **Entity-anchored Machine Translation (EaMaTa)** framework. By leveraging the manually annotated English dataset *FewNERD*, we created a large-scale resource comprising an average of 153k sentences and 354k entities per language. Our analysis demonstrates that EaMaTa provides up to a 9% increase in F1-score against the current state-of-the-art.

## 🛠 The EaMaTa Framework

The **Entity-anchored Machine Translation** framework ensures high-quality translation by:

1. **Preprocessing:** Converting BIO format to entity-anchored text (e.g., using  tags).
2. **Translation:** Translating both plain and anchored versions.
3. **Cleaning:** A three-stage pipeline to discard sentences with mismatches in structure, anchor boundaries, or entity counts.

---

<img src="https://github.com/PrachuryyaKaushik/SampurNER/blob/main/EaMaTa_framework_final_poster-1.png" alt="Entity-anchored Machine Translation: The source dataset is translated both as `Plain sentence' and `Entity-anchored sentence' to the target languages. The cleaning process includes the removal of sentences with sentence mismatch, entity-anchor boundaries mismatch (both start and end), and total entity counts mismatch between the source and translated sentences." width="500">


## 📊 Dataset Statistics

Statistics for the generated datasets across 22 languages along with the source FewNERD (English) dataset. Sent, Ent Tok means number of Sentences, Entities and Tokens respectively.

<table>
  <thead>
    <tr>
      <th rowspan="2">Language</th>
      <th colspan="3">Train Set</th>
      <th colspan="3">Development Set</th>
      <th colspan="3">Silver Test Set</th>
    </tr>
    <tr>
      <th>Sentences</th>
      <th>Entities</th>
      <th>Tokens</th>
      <th>Sentences</th>
      <th>Entities</th>
      <th>Tokens</th>
      <th>Sentences</th>
      <th>Entities</th>
      <th>Tokens</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><b>Assamese</b></td><td>107,249</td><td>237,260</td><td>2,194,925</td><td>15,438</td><td>34,560</td><td>318,105</td><td>30,658</td><td>67,466</td><td>625,870</td></tr>
    <tr><td><b>Bengali</b></td><td>119,296</td><td>287,264</td><td>2,484,304</td><td>17,513</td><td>42,877</td><td>368,063</td><td>33,374</td><td>79,340</td><td>689,690</td></tr>
    <tr><td><b>Bodo</b></td><td>117,659</td><td>262,792</td><td>2,354,696</td><td>16,762</td><td>37,496</td><td>336,269</td><td>33,615</td><td>74,576</td><td>672,246</td></tr>
    <tr><td><b>Dogri</b></td><td>112,329</td><td>264,154</td><td>2,885,149</td><td>17,619</td><td>42,526</td><td>459,537</td><td>34,931</td><td>82,597</td><td>903,796</td></tr>
    <tr><td><b>Gujarati</b></td><td>126,581</td><td>315,919</td><td>2,828,298</td><td>18,122</td><td>45,431</td><td>406,929</td><td>28,959</td><td>69,207</td><td>619,889</td></tr>
    <tr><td><b>Hindi</b></td><td>124,887</td><td>290,192</td><td>3,298,116</td><td>17,882</td><td>41,824</td><td>457,573</td><td>35,713</td><td>82,440</td><td>908,513</td></tr>
    <tr><td><b>Kannada</b></td><td>115,565</td><td>266,523</td><td>2,083,241</td><td>16,962</td><td>39,781</td><td>308,326</td><td>26,327</td><td>59,365</td><td>453,817</td></tr>
    <tr><td><b>Kashmiri</b></td><td>123,679</td><td>288,544</td><td>2,910,937</td><td>17,417</td><td>40,350</td><td>408,053</td><td>35,106</td><td>81,181</td><td>823,040</td></tr>
   <tr><td><b>Konkani</b></td><td>83,415</td><td>182,806</td><td>1,637,018</td><td>12,276</td><td>27,262</td><td>243,817</td><td>23,759</td><td>51,483</td><td>463,980</td></tr>
    <tr><td><b>Maithili</b></td><td>108,826</td><td>256,701</td><td>2,763,005</td><td>10,224</td><td>22,706</td><td>245,657</td><td>19,899</td><td>43,530</td><td>472,498</td></tr>
    <tr><td><b>Malayalam</b></td><td>91,743</td><td>199,485</td><td>1,504,839</td><td>15,608</td><td>35,140</td><td>265,049</td><td>23,480</td><td>50,319</td><td>377,213</td></tr>
    <tr><td><b>Manipuri</b></td><td>110,068</td><td>246,084</td><td>2,264,925</td><td>15,561</td><td>34,869</td><td>321,556</td><td>31,463</td><td>69,739</td><td>644,709</td></tr>
    <tr><td><b>Marathi</b></td><td>125,543</td><td>309,220</td><td>2,614,024</td><td>17,650</td><td>43,407</td><td>367,882</td><td>36,237</td><td>89,295</td><td>754,851</td></tr>
    <tr><td><b>Nepali</b></td><td>125,695</td><td>311,439</td><td>2,661,064</td><td>18,252</td><td>45,778</td><td>389,382</td><td>35,498</td><td>87,112</td><td>747,802</td></tr>
    <tr><td><b>Odia</b></td><td>118,633</td><td>289,943</td><td>2,427,051</td><td>18,090</td><td>45,247</td><td>376,152</td><td>32,477</td><td>78,893</td><td>657,395</td></tr>
    <tr><td><b>Punjabi</b></td><td>96,986</td><td>234,436</td><td>2,348,393</td><td>17,655</td><td>44,415</td><td>443,788</td><td>36,920</td><td>92,655</td><td>928,798</td></tr>
    <tr><td><b>Sanskrit</b></td><td>69,581</td><td>152,269</td><td>1,214,021</td><td>10,043</td><td>22,175</td><td>176,574</td><td>19,729</td><td>42,643</td><td>341,208</td></tr>
    <tr><td><b>Santali</b></td><td>87,650</td><td>153,533</td><td>2,223,951</td><td>12,526</td><td>22,159</td><td>312,706</td><td>24,921</td><td>43,264</td><td>619,556</td></tr>
    <tr><td><b>Sindhi</b></td><td>90,362</td><td>214,371</td><td>2,218,078</td><td>17,221</td><td>42,845</td><td>440,340</td><td>32,159</td><td>78,317</td><td>809,085</td></tr>
    <tr><td><b>Tamil</b></td><td>96,004</td><td>216,285</td><td>1,711,203</td><td>10,702</td><td>23,542</td><td>183,893</td><td>25,160</td><td>55,927</td><td>441,141</td></tr>
    <tr><td><b>Telugu</b></td><td>85,893</td><td>193,425</td><td>1,505,321</td><td>16,790</td><td>39,909</td><td>309,345</td><td>21,729</td><td>47,988</td><td>372,946</td></tr>
    <tr><td><b>Urdu</b></td><td>122,794</td><td>298,069</td><td>3,229,867</td><td>17,570</td><td>43,205</td><td>465,417</td><td>35,198</td><td>85,785</td><td>929,427</td></tr>
    <tr><td><b>FewNERD</b></td><td>131,767</td><td>340,387</td><td>3,359,329</td><td>18,824</td><td>48,770</td><td>482,037</td><td>37,648</td><td>96,902</td><td>958,765</td></tr>
  </tbody>
</table>

---

## 📈 Experimental Results (F1-Scores)

Performance of **mBERT** and **IndicBERTv2** models fine-tuned on SampurNER.
<table>
  <thead>
    <tr>
      <th rowspan="2">Language</th>
      <th colspan="3">mBERT (Micro)</th>
      <th colspan="3">IndicBERTv2 (Micro)</th>
    </tr>
    <tr>
      <th>P</th>
      <th>R</th>
      <th>F1</th>
      <th>P</th>
      <th>R</th>
      <th>F1</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><b>FewNERD (en)</b></td><td>65.2</td><td>69.1</td><td>67.1</td><td>64.0</td><td>68.2</td><td>66.0</td></tr>
    <tr><td><b>Assamese</b></td><td>60.1</td><td>63.7</td><td>61.8</td><td>62.6</td><td>66.2</td><td>64.4</td></tr>
    <tr><td><b>Bengali</b></td><td>62.3</td><td>65.5</td><td>63.8</td><td>64.4</td><td>67.7</td><td>66.0</td></tr>
    <tr><td><b>Bodo</b></td><td>61.2</td><td>64.7</td><td>62.9</td><td>63.6</td><td>66.7</td><td>65.1</td></tr>
    <tr><td><b>Dogri</b></td><td>58.1</td><td>61.8</td><td>59.9</td><td>59.3</td><td>63.6</td><td>61.4</td></tr>
    <tr><td><b>Gujarati</b></td><td>62.2</td><td>65.2</td><td>63.7</td><td>64.8</td><td>67.9</td><td>66.3</td></tr>
    <tr><td><b>Hindi</b></td><td>59.7</td><td>63.2</td><td>61.4</td><td>61.1</td><td>63.8</td><td>62.4</td></tr>
    <tr><td><b>Kannada</b></td><td>61.4</td><td>64.9</td><td>63.1</td><td>63.8</td><td>67.0</td><td>65.4</td></tr>
    <tr><td><b>Kashmiri</b></td><td>58.4</td><td>61.8</td><td>60.1</td><td>59.3</td><td>63.3</td><td>61.2</td></tr>
    <tr><td><b>Konkani</b></td><td>57.7</td><td>61.8</td><td>59.7</td><td>60.0</td><td>63.9</td><td>61.9</td></tr>
    <tr><td><b>Maithili</b></td><td>58.4</td><td>61.9</td><td>60.1</td><td>60.2</td><td>64.3</td><td>62.2</td></tr>
    <tr><td><b>Malayalam</b></td><td>58.8</td><td>62.1</td><td>60.4</td><td>62.0</td><td>65.4</td><td>63.6</td></tr>
    <tr><td><b>Manipuri</b></td><td>25.3</td><td>7.3</td><td>11.3</td><td>55.6</td><td>58.8</td><td>57.2</td></tr>
    <tr><td><b>Marathi</b></td><td>63.4</td><td>66.5</td><td>64.9</td><td>64.8</td><td>68.1</td><td>66.4</td></tr>
    <tr><td><b>Nepali</b></td><td>64.2</td><td>67.1</td><td>65.6</td><td>65.7</td><td>68.5</td><td>67.1</td></tr>
    <tr><td><b>Odia</b></td><td>32.0</td><td>11.4</td><td>16.8</td><td>63.1</td><td>66.4</td><td>64.7</td></tr>
    <tr><td><b>Punjabi</b></td><td>58.7</td><td>61.9</td><td>60.3</td><td>61.2</td><td>65.1</td><td>63.1</td></tr>
    <tr><td><b>Sanskrit</b></td><td>59.6</td><td>63.0</td><td>61.3</td><td>60.7</td><td>64.7</td><td>62.6</td></tr>
    <tr><td><b>Santali</b></td><td>43.0</td><td>15.5</td><td>22.8</td><td>50.6</td><td>51.8</td><td>51.2</td></tr>
    <tr><td><b>Sindhi</b></td><td>43.3</td><td>42.7</td><td>43.0</td><td>57.9</td><td>61.6</td><td>59.7</td></tr>
    <tr><td><b>Tamil</b></td><td>59.9</td><td>63.2</td><td>61.5</td><td>61.3</td><td>64.8</td><td>63.0</td></tr>
    <tr><td><b>Telugu</b></td><td>59.5</td><td>62.8</td><td>61.1</td><td>62.4</td><td>65.8</td><td>64.1</td></tr>
    <tr><td><b>Urdu</b></td><td>60.3</td><td>63.8</td><td>62.0</td><td>60.7</td><td>64.5</td><td>62.6</td></tr>
  </tbody>
</table>

---

## 🚀 How to Use

### Loading the Dataset

```python
from datasets import load_dataset
dataset = load_dataset("prachuryyaIITG/SampurNER")

```

## 🚀 More resources

* [Fine-tuned models](https://huggingface.co/collections/prachuryyaIITG/sampurner)
* [Interactive Demo](https://huggingface.co/spaces/prachuryyaIITG/SampurNER-Demo)
* [Agentic tool: AWED-FiNER](https://github.com/PrachuryyaKaushik/AWED-FiNER)

### Citation

```bibtex
@inproceedings{kaushik2026sampurner,
  title={SampurNER: Fine-grained Named Entity Recognition dataset for 22 Indian Languages},
  author={Kaushik, Prachuryya and Anand, Ashish},
  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
  volume={40},
  year={2026}
}


```

---

**Maintained by:** [Prachuryya Kaushik](https://huggingface.co/prachuryyaIITG)

---
