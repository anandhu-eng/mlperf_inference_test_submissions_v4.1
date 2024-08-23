This experiment is generated using the [MLCommons Collective Mind automation framework (CM)](https://github.com/mlcommons/cm4mlops).

*Check [CM MLPerf docs](https://docs.mlcommons.org/inference) for more details.*

## Host platform

* OS version: Linux-6.8.0-38-generic-x86_64-with-glibc2.39
* CPU version: x86_64
* Python version: 3.12.3 (main, Jul 31 2024, 17:43:48) [GCC 13.2.0]
* MLCommons CM version: 2.3.1

## CM Run Command

See [CM installation guide](https://docs.mlcommons.org/inference/install/).

```bash
pip install -U cmind

cm rm cache -f

cm pull repo anandhu-eng@cm4mlops --checkout=90af227565e7424ed200ba61852e6b0652fe44a4

cm run script \
	--tags=run-mlperf,inference,_r4.1 \
	--model=bert-99 \
	--implementation=reference \
	--framework=deepsparse \
	--category=edge \
	--scenario=Offline \
	--execution_mode=valid \
	--device=cuda \
	--quiet \
	--env.CM_MLPERF_NEURALMAGIC_MODEL_ZOO_STUB=zoo:nlp/question_answering/mobilebert-none/pytorch/huggingface/squad/base_quant-none \
	--adr.cuda.version=12.4.1
```
*Note that if you want to use the [latest automation recipes](https://docs.mlcommons.org/inference) for MLPerf (CM scripts),
 you should simply reload anandhu-eng@cm4mlops without checkout and clean CM cache as follows:*

```bash
cm rm repo anandhu-eng@cm4mlops
cm pull repo anandhu-eng@cm4mlops
cm rm cache -f

```

## Results

Platform: intel_spr_i9-reference-gpu-deepsparse_v1.8.0-default_config

Model Precision: open

### Accuracy Results 
`F1`: `90.81269`, Required accuracy for closed division `>= 89.96526`

### Performance Results 
`Samples per second`: `108.409`
