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
##### IUPred2A
	​	nohup python GetFeature_iupred2a.py ../data/benchmark/humvar_tool_scores.csv humvar long > log/GetFeature_iupred2a_humvar_long.log &
	​	nohup python GetFeature_iupred2a.py ../data/benchmark/humvar_tool_scores.csv humvar short > log/GetFeature_iupred2a_humvar_short.log &
	
	​	nohup python GetFeature_iupred2a.py ../data/benchmark/exovar_tool_scores.csv exovar long > log/GetFeature_iupred2a_exovar_long.log &
	​	nohup python GetFeature_iupred2a.py ../data/benchmark/exovar_tool_scores.csv exovar short > log/GetFeature_iupred2a_exovar_short.log &
	
	​	nohup python GetFeature_iupred2a.py ../data/benchmark/varibench_selected_tool_scores.csv varibench long > log/GetFeature_iupred2a_varibench_long.log &
	​	nohup python GetFeature_iupred2a.py ../data/benchmark/varibench_selected_tool_scores.csv varibench short > log/GetFeature_iupred2a_varibench_short.log &
	
	​	nohup python GetFeature_iupred2a.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar long > log/GetFeature_iupred2a_swissvar_long.log &
	​	nohup python GetFeature_iupred2a.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar short > log/GetFeature_iupred2a_swissvar_short.log &
	
	​	nohup python GetFeature_iupred2a.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP long > log/GetFeature_iupred2a_predictSNP_long.log &
	​	nohup python GetFeature_iupred2a.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP short > log/GetFeature_iupred2a_predictSNP_short.log &
	
##### Espritz
	​	nohup python GetFeature_espritz.py ../data/benchmark/humvar_tool_scores.csv humvar X > log/GetFeature_espritz_X_humvar.log &
	​	nohup python GetFeature_espritz.py ../data/benchmark/humvar_tool_scores.csv humvar N > log/GetFeature_espritz_N_humvar.log &
	​	nohup python GetFeature_espritz.py ../data/benchmark/humvar_tool_scores.csv humvar D > log/GetFeature_espritz_D_humvar.log &
	
	​	nohup python GetFeature_espritz.py ../data/benchmark/exovar_tool_scores.csv exovar D > log/GetFeature_espritz_D_exovar.log &
	​	nohup python GetFeature_espritz.py ../data/benchmark/exovar_tool_scores.csv exovar N > log/GetFeature_espritz_N_exovar.log &
	​	nohup python GetFeature_espritz.py ../data/benchmark/exovar_tool_scores.csv exovar X > log/GetFeature_espritz_X_exovar.log &
	
	​	nohup python GetFeature_espritz.py ../data/benchmark/varibench_selected_tool_scores.csv varibench X > log/GetFeature_espritz_X_varibench.log &
	​	nohup python GetFeature_espritz.py ../data/benchmark/varibench_selected_tool_scores.csv varibench N > log/GetFeature_espritz_N_varibench.log &
	​	nohup python GetFeature_espritz.py ../data/benchmark/varibench_selected_tool_scores.csv varibench D > log/GetFeature_espritz_D_varibench.log &
	
	​	nohup python GetFeature_espritz.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar X > log/GetFeature_espritz_X_varibench.log &
	​	nohup python GetFeature_espritz.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar N > log/GetFeature_espritz_N_varibench.log &
	​	nohup python GetFeature_espritz.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar D > log/GetFeature_espritz_D_varibench.log &
	
	​	nohup python GetFeature_espritz.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP X > log/GetFeature_espritz_X_varibench.log &
	​	nohup python GetFeature_espritz.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP N > log/GetFeature_espritz_N_varibench.log &
	​	nohup python GetFeature_espritz.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP D > log/GetFeature_espritz_D_varibench.log &


##### DisEmbl

	​	nohup python GetFeature_disembl.py ../data/benchmark/humvar_tool_scores.csv humvar coils > log/GetFeature_disembl_coils_humvar.log &
	​	nohup python GetFeature_disembl.py ../data/benchmark/humvar_tool_scores.csv humvar rem465 > log/GetFeature_disembl_rem65_humvar.log &
	​	nohup python GetFeature_disembl.py ../data/benchmark/humvar_tool_scores.csv humvar hotloops > log/GetFeature_disembl_hotloops_humvar.log &

	​	nohup python GetFeature_disembl.py ../data/benchmark/exovar_tool_scores.csv exovar coils > log/GetFeature_disembl_coils_exovar.log &
	​	nohup python GetFeature_disembl.py ../data/benchmark/exovar_tool_scores.csv exovar rem465 > log/GetFeature_disembl_rem65_exovar.log &
	​	nohup python GetFeature_disembl.py ../data/benchmark/exovar_tool_scores.csv exovar hotloops > log/GetFeature_disembl_hotloops_exovar.log &

	​	nohup python GetFeature_disembl.py ../data/benchmark/varibench_selected_tool_scores.csv varibench coils > log/GetFeature_disembl_coils_varibench.log &
	​	nohup python GetFeature_disembl.py ../data/benchmark/varibench_selected_tool_scores.csv varibench rem465 > log/GetFeature_disembl_rem65_varibench.log &
	​	nohup python GetFeature_disembl.py ../data/benchmark/varibench_selected_tool_scores.csv varibench hotloops > log/GetFeature_disembl_hotloops_varibench.log &

	​	nohup python GetFeature_disembl.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar coils > log/GetFeature_disembl_coils_swissvar.log &
	​	nohup python GetFeature_disembl.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar rem465 > log/GetFeature_disembl_rem65_swissvar.log &
	​	nohup python GetFeature_disembl.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar hotloops > log/GetFeature_disembl_hotloops_swissvar.log &

	​	nohup python GetFeature_disembl.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP coils > log/GetFeature_disembl_coils_predictSNP.log &
	​	nohup python GetFeature_disembl.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP rem465 > log/GetFeature_disembl_rem65_predictSNP.log &
	​	nohup python GetFeature_disembl.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP hotloops > log/GetFeature_disembl_hotloops_predictSNP.log &


### 5.2 Disorder Promotion Feature (DPF)
	​	nohup python GetFeature_PromoptResidue.py ../data/benchmark/humvar_tool_scores.csv humvar > log/GetFeature_PromoptResidue_humvar.log &
	​	nohup python GetFeature_PromoptResidue.py ../data/benchmark/exovar_tool_scores.csv exovar > log/GetFeature_PromoptResidue_exovar.log &
	​	nohup python GetFeature_PromoptResidue.py ../data/benchmark/varibench_selected_tool_scores.csv varibench > log/GetFeature_PromoptResidue_varibench.log &
	​	nohup python GetFeature_PromoptResidue.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar > log/GetFeature_PromoptResidue_swissvar.log &
	​	nohup python GetFeature_PromoptResidue.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP > log/GetFeature_PromoptResidue_predictSNP.log &


### 5.3 Molecular recoginition Region Feature (MoRF)
##### fMoRF webserver (http://biomine.cs.vcu.edu/servers/fMoRFpred/)
	find ../../data/benchmark/ncbi_seq_wildmut/humvar/ *.fasta | xargs cat > humvar_fMoRF.fasta
	find ../../data/benchmark/ncbi_seq_wildmut/exovar/ *.fasta | xargs cat > exovar_fMoRF.fasta
	find ../../data/benchmark/ncbi_seq_wildmut/varibench/ *.fasta | xargs cat > varibench_fMoRF.fasta
	find ../../data/benchmark/ncbi_seq_wildmut/swissvar/ *.fasta | xargs cat > swissvar_fMoRF.fasta
	find ../../data/benchmark/ncbi_seq_wildmut/predictSNP/ *.fasta | xargs cat > predictSNP_fMoRF.fasta
	humvar.split0 http://biomine.cs.vcu.edu/webresults/fMoRFpred/20190527084228/results.html
	humvar.split1 http://biomine.cs.vcu.edu/webresults/fMoRFpred/20190527092937/results.html
	humvar.split2 http://biomine.cs.vcu.edu/webresults/fMoRFpred/20190527100108/results.html
	humvar.split3 http://biomine.cs.vcu.edu/webresults/fMoRFpred/20190527103942/results.html
	humvar.split4 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split5 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split6 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split7 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split8 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split9 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split10 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split11 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split12 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split13 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split14 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split15 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split16 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split17 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split18 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split19 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split20 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split21 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split22 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split23 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split24 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html
	humvar.split25 http://biomine.cs.vcu.edu/webresults/fMoRFpred//results.html

### 5.4 Derived Predicted Disorder Feature (DPDF)
##### IUPred2A
	​	nohup python GetFeature_2_iupred2a.py ../data/benchmark/humvar_tool_scores.csv humvar long > log/GetFeature_2_iupred2a_humvar_long.log &
	​	nohup python GetFeature_2_iupred2a.py ../data/benchmark/humvar_tool_scores.csv humvar short > log/GetFeature_2_iupred2a_humvar_short.log &
	​	nohup python GetFeature_2_iupred2a.py ../data/benchmark/exovar_tool_scores.csv exovar long > log/GetFeature_2_iupred2a_exovar_long.log &
	​	nohup python GetFeature_2_iupred2a.py ../data/benchmark/exovar_tool_scores.csv exovar short > log/GetFeature_2_iupred2a_exovar_short.log &
	​	nohup python GetFeature_2_iupred2a.py ../data/benchmark/varibench_selected_tool_scores.csv varibench long > log/GetFeature_2_iupred2a_varibench_long.log &
	​	nohup python GetFeature_2_iupred2a.py ../data/benchmark/varibench_selected_tool_scores.csv varibench short > log/GetFeature_2_iupred2a_varibench_short.log &
	​	nohup python GetFeature_2_iupred2a.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar long > log/GetFeature_2_iupred2a_swissvar_long.log &
	​	nohup python GetFeature_2_iupred2a.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar short > log/GetFeature_2_iupred2a_swissvar_short.log &
	​	nohup python GetFeature_2_iupred2a.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP long > log/GetFeature_2_iupred2a_predictSNP_long.log &
	​	nohup python GetFeature_2_iupred2a.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP short > log/GetFeature_2_iupred2a_predictSNP_short.log &
##### Espritz
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/humvar_tool_scores.csv humvar X > log/GetFeature_2_espritz_derived_humvar_espritz_X.log &
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/humvar_tool_scores.csv humvar N > log/GetFeature_2_espritz_derived_humvar_espritz_N.log &
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/humvar_tool_scores.csv humvar D > log/GetFeature_2_espritz_derived_humvar_espritz_D.log &

	​	nohup python GetFeature_2_espritz.py ../data/benchmark/exovar_tool_scores.csv exovar X > log/GetFeature_2_espritz_derived_exovar_espritz_X.log &
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/exovar_tool_scores.csv exovar N > log/GetFeature_2_espritz_derived_exovar_espritz_N.log &
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/exovar_tool_scores.csv exovar D > log/GetFeature_2_espritz_derived_exovar_espritz_D.log &

	​	nohup python GetFeature_2_espritz.py ../data/benchmark/varibench_selected_tool_scores.csv varibench X > log/GetFeature_2_espritz_derived_varibench_espritz_X.log &
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/varibench_selected_tool_scores.csv varibench N > log/GetFeature_2_espritz_derived_varibench_espritz_N.log &
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/varibench_selected_tool_scores.csv varibench D > log/GetFeature_2_espritz_derived_varibench_espritz_D.log &

	​	nohup python GetFeature_2_espritz.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar X > log/GetFeature_2_espritz_derived_varibench_espritz_X.log &
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar N > log/GetFeature_2_espritz_derived_varibench_espritz_N.log &
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar D > log/GetFeature_2_espritz_derived_varibench_espritz_D.log &

	​	nohup python GetFeature_2_espritz.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP X > log/GetFeature_2_espritz_derived_predictSNP_espritz_X.log &
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP N > log/GetFeature_2_espritz_derived_predictSNP_espritz_N.log &
	​	nohup python GetFeature_2_espritz.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP D > log/GetFeature_2_espritz_derived_predictSNP_espritz_D.log &
##### DisEmbl
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/humvar_tool_scores.csv humvar coils > derived_disembl_coils_humvar.log & #RESIDUE COILS REM465 HOTLOOPS
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/humvar_tool_scores.csv humvar rem465 > derived_disembl_rem65_humvar.log &
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/humvar_tool_scores.csv humvar hotloops > derived_disembl_hotloops_humvar.log &

	​	nohup python GetFeature_2_disembl.py ../data/benchmark/exovar_tool_scores.csv exovar coils > derived_disembl_coils_exovar.log &
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/exovar_tool_scores.csv exovar rem465 > derived_disembl_rem65_exovar.log &
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/exovar_tool_scores.csv exovar hotloops > derived_disembl_hotloops_exovar.log &

	​	nohup python GetFeature_2_disembl.py ../data/benchmark/varibench_selected_tool_scores.csv varibench coils > derived_disembl_coils_varibench.log &
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/varibench_selected_tool_scores.csv varibench rem465 > derived_disembl_rem65_varibench.log &
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/varibench_selected_tool_scores.csv varibench hotloops > derived_disembl_hotloops_varibench.log &

	​	nohup python GetFeature_2_disembl.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar coils > derived_disembl_coils_swissvar.log &
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar rem465 > derived_disembl_rem65_swissvar.log &
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar hotloops > derived_disembl_hotloops_swissvar.log &

	​	nohup python GetFeature_2_disembl.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP coils > derived_disembl_coils_predictSNP.log &
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP rem465 > derived_disembl_rem65_predictSNP.log &
	​	nohup python GetFeature_2_disembl.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP hotloops > derived_disembl_hotloops_predictSNP.log &

### 5.5 Polyphen2 Consevation Features (PPH2)

## 6 Feature Evalutation & Comparison
	​	python EvaluateFeatures.py ../data/benchmark/exovar_tool_scores.csv exovar
	​	python EvaluateFeatures.py ../data/benchmark/humvar_tool_scores.csv humvar
	​	python EvaluateFeatures.py ../data/benchmark/varibench_selected_tool_scores.csv varibench
	​	python EvaluateFeatures.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar
	​	python EvaluateFeatures.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP

	​	nohup python PredictionComparison.py ../data/benchmark/humvar_tool_scores.csv humvar roc_auc > log/PredictionComparison_humvar.log &
	​	nohup python PredictionComparison.py ../data/benchmark/exovar_tool_scores.csv exovar roc_auc > log/PredictionComparison_exovar.log &
	​	nohup python PredictionComparison.py ../data/benchmark/varibench_selected_tool_scores.csv varibench roc_auc > log/PredictionComparison_varibench.log &
	​	nohup python PredictionComparison.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar roc_auc > log/PredictionComparison_swissvar.log &
	​	nohup python PredictionComparison.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP roc_auc > log/PredictionComparison_predictSNP.log &


	​	python PreDefinedPrediction.py ../data/benchmark/exovar_tool_scores.csv exovar
	​	python PreDefinedPrediction.py ../data/benchmark/humvar_tool_scores.csv humvar
	​	python PreDefinedPrediction.py ../data/benchmark/varibench_selected_tool_scores.csv varibench
	​	python PreDefinedPrediction.py ../data/benchmark/swissvar_selected_tool_scores.csv swissvar
	​	python PreDefinedPrediction.py ../data/benchmark/predictSNP_selected_tool_scores.csv predictSNP

