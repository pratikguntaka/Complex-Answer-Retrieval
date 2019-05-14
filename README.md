# Complex-Answer-Retrieval

Within a python IDE, after you have gone to the directory of where Pratik's ranking files are located, 
enter the following command: 

##############
python gen_rankings.py train.benchmarkY1train.cbor.outlines train.benchmarkY1train.cbor.paragraphs output.prox.run PROX no_cache 100
##############

the above command will create in the same directory, a run file called: "output.prox"
then within this same directory, enter the following command to produce MRR, Rprec and MAP: 
#############
python eval_framework.py train.benchmarkY1train.cbor.hierarchical.qrels output.prox
#############

-----------------------------------------------------------------------------------------------------
Then, copy the generated run file "output.prox" and "train.benchmarkY1train.cbor.hierarchical.qrels"
 to the directory where trec_eval content is located, this directory should have all the evaluation files 
m_num_ret.c, m_num_rel.c, m_map.c, etc.   In this directory, enter the following command: 

############
./trec_eval -m runid -m num_q -m num_ret -m num_rel -m map train.benchmarkY1train.cbor.hierarchical.qrels output.prox.run
############
