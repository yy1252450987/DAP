## 1. Sequence Process
　### 1.1 Download fasta sequences from NCBI and Uniprot database
	​	python DownloadNcbiSeq.py ../data/benchmark/humvar_tool_scores.csv humvar
 	​	python DownloadNcbiSeq.py ../data/benchmark/exovar_tool_scores.csv exovar 
 	​	python DownloadNcbiSeq.py ../data/benchmark/varibench_selected_tool_scores.csv varibench
 	​	python DownloadNcbiSeq.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar
 	​	python DownloadNcbiSeq.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP
　### 1.2 Extract wild and mutate sequences from downloaded sequences
	​	python WildSeq2MutSeq.py 

## 2. Disorder Prediction
	### 2.1 IUPred2A
	​	nohup python DisorderPredict_iupred2a.py ../data/benchmark/humvar_tool_scores.csv humvar long > log/DisorderPredict_iupred2a_humvar_long.log &
	​	nohup python DisorderPredict_iupred2a.py ../data/benchmark/humvar_tool_scores.csv humvar short > log/DisorderPredict_iupred2a_humvar_short.log &
	
	​	nohup python DisorderPredict_iupred2a.py ../data/benchmark/exovar_tool_scores.csv exovar long > log/DisorderPredict_iupred2a_exovar_long.log &
	​	nohup python DisorderPredict_iupred2a.py ../data/benchmark/exovar_tool_scores.csv exovar short > log/DisorderPredict_iupred2a_exovar_short.log &
	
	​	nohup python DisorderPredict_iupred2a.py ../data/benchmark/varibench_selected_tool_scores.csv varibench long > log/DisorderPredict_iupred2a_varibench_long.log &
	​	nohup python DisorderPredict_iupred2a.py ../data/benchmark/varibench_selected_tool_scores.csv varibench short > log/DisorderPredict_iupred2a_varibench_short.log &
	
	​	nohup python DisorderPredict_iupred2a.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar long > log/DisorderPredict_iupred2a_swissvar_long.log &
	​	nohup python DisorderPredict_iupred2a.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar short > log/DisorderPredict_iupred2a_swissvar_short.log &
	
	​	nohup python DisorderPredict_iupred2a.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP long > log/DisorderPredict_iupred2a_predictSNP_long.log &
	​	nohup python DisorderPredict_iupred2a.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP short > log/DisorderPredict_iupred2a_predictSNP_short.log &

### 2.2 Espritz
##### prepare the fasta sequences directory
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/humvar ../result/espritz_N
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/exovar ../result/espritz_N
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/varibench ../result/espritz_N
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/swissvar ../result/espritz_N
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/predictSNP ../result/espritz_N

	​	cp -r ../data/benchmark/ncbi_seq_wildmut/humvar ../result/espritz_D
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/exovar ../result/espritz_D
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/varibench ../result/espritz_D
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/swissvar ../result/espritz_D
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/predictSNP ../result/espritz_D

	​	cp -r ../data/benchmark/ncbi_seq_wildmut/humvar ../result/espritz_X
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/exovar ../result/espritz_X
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/varibench ../result/espritz_X
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/swissvar ../result/espritz_X
	​	cp -r ../data/benchmark/ncbi_seq_wildmut/predictSNP ../result/espritz_X

##### do the prediction (workdir: the directory of software Espritz)
	​	nohup python ../../script/DisorderPredict_espritz.py humvar X > DisorderPredict_espritz_humvar_X.log &
	​	nohup python ../../script/DisorderPredict_espritz.py exovar X > DisorderPredict_espritz_exovar_X.log &
	​	nohup python ../../script/DisorderPredict_espritz.py varibench X > DisorderPredict_espritz_varibench_X.log &
	​	nohup python ../../script/DisorderPredict_espritz.py swissvar X > DisorderPredict_espritz_swissvar_X.log &
	​	nohup python ../../script/DisorderPredict_espritz.py predictSNP X > DisorderPredict_espritz_predictSNP_X.log &

	​	nohup python ../../script/DisorderPredict_espritz.py humvar N > DisorderPredict_espritz_humvar_N.log &
	​	nohup python ../../script/DisorderPredict_espritz.py exovar N > DisorderPredict_espritz_exovar_N.log &
	​	nohup python ../../script/DisorderPredict_espritz.py varibench N > DisorderPredict_espritz_varibench_N.log &
	​	nohup python ../../script/DisorderPredict_espritz.py swissvar N > DisorderPredict_espritz_swissvar_N.log &
	​	nohup python ../../script/DisorderPredict_espritz.py predictSNP N > DisorderPredict_espritz_predictSNP_N.log &

	​	nohup python ../../script/DisorderPredict_espritz.py humvar D > DisorderPredict_espritz_humvar_D.log &
	​	nohup python ../../script/DisorderPredict_espritz.py exovar D > DisorderPredict_espritz_exovar_D.log &
	​	nohup python ../../script/DisorderPredict_espritz.py varibench D > DisorderPredict_espritz_varibench_D.log &
	​	nohup python ../../script/DisorderPredict_espritz.py swissvar D > DisorderPredict_espritz_swissvar_D.log &
	​	nohup python ../../script/DisorderPredict_espritz.py predictSNP D > DisorderPredict_espritz_predictSNP_D.log &


### 2.3 DisEmbl
	​	nohup python DisorderPredict_disembl.py ../data/benchmark/humvar_tool_scores.csv humvar > log/DisorderPredict_disembl_humvar.log &
	​	nohup python DisorderPredict_disembl.py ../data/benchmark/exovar_tool_scores.csv exovar > log/DisorderPredict_disembl_exovar.log &
	​	nohup python DisorderPredict_disembl.py ../data/benchmark/varibench_selected_tool_scores.csv varibench > log/DisorderPredict_disembl_varibench.log &
	​	nohup python DisorderPredict_disembl.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar > log/DisorderPredict_disembl_swissvar.log &
	​	nohup python DisorderPredict_disembl.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP > log/DisorderPredict_disembl_predictSNP.log &

## 3.Molecular recoginition Region Feature(MoRF)

## 4.PolyPhen2
### 4.1 Prepare the input files for polyhhen2 prediction

	​	python Prepare_pph2.py

### 4.2 Download polyphen2 predition results
  ##### HumVar
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/17/pph2-snps.txt -O humvar.pph2-snps.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/17/pph2-short.txt -O humvar.pph2-short.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/17/pph2-full.txt -O humvar.pph2-full.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/17/pph2-log.txt -O humvar.pph2-logs.txt
  ##### ExoVar
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/18/pph2-snps.txt -O exovar.pph2-snps.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/18/pph2-short.txt -O exovar.pph2-short.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/18/pph2-full.txt -O exovar.pph2-full.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/18/pph2-log.txt -O exovar.pph2-logs.txt
  ##### VariBench
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/20/pph2-snps.txt -O varibench.pph2-snps.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/20/pph2-short.txt -O varibench.pph2-short.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/20/pph2-full.txt -O varibench.pph2-full.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/20/pph2-log.txt -O varibench.pph2-logs.txt
  ##### SwissVar
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/23/pph2-snps.txt -O swissvar.pph2-snps.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/23/pph2-short.txt -O swissvar.pph2-short.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/23/pph2-full.txt -O swissvar.pph2-full.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/23/pph2-log.txt -O swissvar.pph2-logs.txt
  ##### PredictSNP
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/24/pph2-snps.txt -O predictSNP.pph2-snps.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/24/pph2-short.txt -O predictSNP.pph2-short.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/24/pph2-full.txt -O predictSNP.pph2-full.txt
	​	wget -b http://genetics.bwh.harvard.edu/ggi/pph2/d07ef4ba93bd556f2b9e9c541a89420e79d8b96b/24/pph2-log.txt -O predictSNP.pph2-logs.txt

### 4.3 Mapping to benchmark dataset
	​	python getPPH2Feature.py



## 5. Feature Combination
### 5.1 Predictted Disorder Score (PDS)
### 5.2 Disorder Promotion Feature (DPF)
### 5.3 Molecular recoginition Region Feature (MoRF)
### 5.4 Derived Predicted Disorder Feature (DPDF)
### 5.5 Polyphen2 Consevation Features (PPH2)
