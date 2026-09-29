# 土壌VNIRスペクトルによる有機物含有量予測 / Soil Organic-Matter Content Prediction from VNIR Spectra

[紹介ページを開く / Open the presentation page](https://kelly-wk.github.io/soil-vnir-organic-matter/)

> **修復済み・公開版は合成データ / Repaired / public synthetic workflow**  
> 公開ケーススタディ / Public case study

## 概要 / Overview

VNIRスペクトル回帰を、グループ分割・フォールド内前処理・予測区間まで含めて再設計した事例。

A redesigned VNIR spectral-regression workflow with grouped splits, fold-local preprocessing, and predictive intervals.

## 主なポイント / Highlights

1. **スペクトル前処理と特徴選択を交差検証フォールド内へ移し、情報漏洩を防止。**  
   Moved spectral preprocessing and feature selection inside cross-validation folds to prevent leakage.
2. **52サイトの公開合成フィクスチャで、グループ分割を含む全工程を再実行可能。**  
   A public synthetic 52-site fixture supports a clean rerun of the full grouped workflow.
3. **複数回帰器の比較に加え、split conformal法による予測不確実性を実装。**  
   Implemented split-conformal predictive uncertainty alongside comparison of multiple regressors.

## 研究の流れ / Research Flow

| 段階 / Stage | 内容 / Evidence |
|---|---|
| **課題 / Problem** | 高次元スペクトルから土壌有機物を予測する際のリークと過度に楽観的な評価を抑える。<br>Reduce leakage and overly optimistic evaluation when predicting soil organic matter from high-dimensional spectra. |
| **方法 / Method** | Ridge、PLS、LASSOを、サイト単位のネスト交差検証とフォールド内前処理で比較する。<br>Compare Ridge, PLS, and LASSO with site-grouped nested cross-validation and fold-local preprocessing. |
| **検証 / Validation** | 公開合成データで再現性を確認し、グループ外評価と適合型予測区間を用いる。<br>Validate reproducibility on public synthetic data using held-out groups and conformal prediction intervals. |
| **成果 / Outcome** | 実データを公開せずに、監査可能なモデリング手順と不確実性評価を提示。<br>Demonstrates an auditable modeling and uncertainty workflow without publishing the real dataset. |

## 使用手法 / Methods

scikit-learn, Ridge regression, PLS regression, LASSO, Nested grouped cross-validation, Split conformal prediction

## 限界と適用範囲 / Limitations & Scope

- 実データにはサイト・年・装置の十分なメタデータがなく、公開版の合成結果は圃場実装性能を示さない。  
  The real data lack sufficient site, year, and instrument metadata, and synthetic results do not establish field-deployment performance.

## 公開範囲 / Publication Boundary

実データは非公開。公開ページの図表と数値はすべて合成フィクスチャ由来で、方法と検証手順のみを紹介する。

The real data remain private. Every public figure and number comes from a synthetic fixture and is used only to present the method and validation workflow.

---

この文書は公開可能な範囲だけで構成されています。  
This document contains only material cleared for public presentation.
