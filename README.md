# JGovCCC-PDL

【日本語は下部に記載しています。】

**JGovCCC-PDL** (*Japanese Government Contract Clause Corpus based on Public Data License*) is a Japanese Legal corpus for clause-type classification in public procurement contracts.

The corpus contains clauses extracted from publicly available standard contract templates, terms and conditions, general conditions, and related procurement documents published by Japanese national and local public institutions as of January 2026. Each clause is annotated with a two-level label hierarchy: a fine-grained clause type (`label_lv2`, 50 classes) and a coarse category (`label_lv1`, 9 classes).

This corpus is intended to support research on Japanese contract-oriented Legal NLP.

## Corpus overview

| Domain | Clauses | Documents | Public institutions | Fine-grained labels |
|---|---:|---:|---:|---:|
| `national` | 6,577 | 156 | 22 | 50 |
| `local` | 2,704 | 56 | 10 | 47 |
| **All** | **9,281** | **212** | **32** | **50** |

The corpus is based on template-style public procurement documents rather than project-specific executed contracts. This design reduces the risk of including sensitive or personally identifiable information while preserving recurring clause functions found in public-sector contracting.

## Annotation labels

Each clause has two labels:

- `label_lv2`: fine-grained clause type, used as the main classification target.
- `label_lv1`: coarse-grained category, mapped from `label_lv2`.

The 9 coarse categories are:

| `label_lv1` | English gloss | Clauses |
|---|---|---:|
| 履行・管理 | Performance and Administration | 2,392 |
| 保証・責任・制裁 | Warranties, Liability, and Sanctions | 1,433 |
| 契約終了・紛争 | Contract Termination and Disputes | 1,404 |
| 変更・リスク | Change and Risk | 1,172 |
| 金銭・会計 | Money and Accounting | 1,018 |
| 権利・情報 | Rights and Information | 930 |
| 契約一般・コミュニケーション | General Terms and Communication | 642 |
| コンプライアンス | Compliance | 193 |
| その他 | Other | 97 |

## Data format

The main corpus file is `jgovccc-pdl.jsonl`. Each line is a JSON object representing one clause.

| Field | Description |
|---|---|
| `provision` | Clause body text |
| `label_lv1` | Coarse-grained clause category |
| `label_lv2` | Fine-grained clause-type label |
| `heading` | Clause heading, when available |
| `national_or_local` | Source domain: `national` or `local` |
| `publisher` | Public institution that published the source document |
| `source_document_name` | Name of the source document |
| `source` | Source URL for the original public document |

## Scope and limitations

JGovCCC-PDL is a licensed, template-focused benchmark for Japanese public procurement contracts. It should not be interpreted as a statistically representative sample of all Japanese contracts, private-sector contracts, or all public procurement practices.

The corpus is provided for research on Legal NLP and contract analysis. It is not legal advice.

## License

The source documents were selected from materials released under terms equivalent to CC BY 4.0, such as the Japanese Public Data License Version 1.0 or comparable terms that permit reproduction, public transmission, and adaptation with appropriate attribution. Each line in this corpus is accompanied by information indicating its source.

This corpus is released under the Apache License 2.0.

## Citation

If you use this corpus, please cite the paper below. 

```bibtex
@inproceedings{doi_yairi_2026_jgovccc_pdl,
  title     = {JGovCCC-PDL: Japanese Government Contract Clause Corpus based on Public Data License},
  author    = {Doi, Nobushige and Yairi, Takehisa},
  booktitle = {ICAIL 2026 Workshop on Artificial Intelligence and Open Government},
  year      = {2026},
  address   = {Singapore, Singapore}
}
```



---

# JGovCCC-PDL（日本語訳）

**JGovCCC-PDL**（*Japanese Government Contract Clause Corpus based on Public Data License*）は、公共調達契約における条項類型分類のための日本語の法ドメインに関するコーパスです。

本コーパスには、2026年1月までに日本の政府および地方公共団体により公開された、標準契約書、約款、契約一般条件、公共調達関連文書から抽出した条項が含まれています。各条項には、細分類の条項タイプ（`label_lv2`、50クラス）と粗分類カテゴリ（`label_lv1`、9クラス）からなる2階層のラベルが付与されています。

本コーパスは、日本語契約文書を対象とする、法ドメインの自然言語処理に関する研究を支援することを目的としています。

## データセット概要

| 区分 | 条項数 | 文書数 | 公的機関数 | 細分類ラベル数 |
|---|---:|---:|---:|---:|
| `national` | 6,577 | 156 | 22 | 50 |
| `local` | 2,704 | 56 | 10 | 47 |
| **全体** | **9,281** | **212** | **32** | **50** |

本コーパスは、個別案件で締結された契約書ではなく、テンプレート形式の公共調達文書を対象としています。この設計により、公共部門の契約に見られる反復的な条項機能を保持しつつ、機微情報や個人情報を含むリスクを低減しています。

## アノテーションラベル

各条項には、以下の2種類のラベルが付与されています。

- `label_lv2`: 主な分類対象となる細分類の条項タイプ。
- `label_lv1`: `label_lv2` から対応付けられる粗分類カテゴリ。

9種類の粗分類カテゴリは以下のとおりです。

| `label_lv1` | 英語表記 | 条項数 |
|---|---|---:|
| 履行・管理 | Performance and Administration | 2,392 |
| 保証・責任・制裁 | Warranties, Liability, and Sanctions | 1,433 |
| 契約終了・紛争 | Contract Termination and Disputes | 1,404 |
| 変更・リスク | Change and Risk | 1,172 |
| 金銭・会計 | Money and Accounting | 1,018 |
| 権利・情報 | Rights and Information | 930 |
| 契約一般・コミュニケーション | General Terms and Communication | 642 |
| コンプライアンス | Compliance | 193 |
| その他 | Other | 97 |

## データ形式

メインのコーパスファイルは `jgovccc-pdl.jsonl` です。各行は、1つの条項を表すJSONオブジェクトです。

| フィールド | 説明 |
|---|---|
| `provision` | 条項本文 |
| `label_lv1` | 粗分類の条項カテゴリ |
| `label_lv2` | 細分類の条項タイプラベル |
| `heading` | 条項見出し（取得可能な場合） |
| `national_or_local` | 出典区分：`national` または `local` |
| `publisher` | 出典文書を公開した公的機関 |
| `source_document_name` | 出典文書名 |
| `source` | 元の公開文書のURL |

## スコープと限界

JGovCCC-PDLは、日本語による、公共調達契約に関するベンチマークです。本コーパスを、日本のすべての契約、民間部門の契約、または公共調達実務全体を統計的に代表するサンプルとして解釈すべきではありません。

本コーパスは、法ドメインにおける自然言語処理および契約分析の研究目的で提供されるものです。法的助言を提供するものではありません。

## ライセンス

出典文書は、CC BY 4.0に相当する、日本の「公共データ利用規約（第1.0版）」または類似する規約に基づき、適切な出典表示を条件として複製、公衆送信、翻案を認める同等の条件で公開された資料から選定されています。本コーパスの各行には、それぞれの出典を示す情報が付与されています。

本コーパスはApache License 2.0で公開いたします。

## 引用

本コーパスを利用する場合は、以下を引用してください。

```bibtex
@inproceedings{doi_yairi_2026_jgovccc_pdl,
  title     = {JGovCCC-PDL: Japanese Government Contract Clause Corpus based on Public Data License},
  author    = {Doi, Nobushige and Yairi, Takehisa},
  booktitle = {ICAIL 2026 Workshop on Artificial Intelligence and Open Government},
  year      = {2026},
  address   = {Singapore, Singapore}
}
```
