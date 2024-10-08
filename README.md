# PhyImpute_UniFracImpute
Two imputation methods, PhyImpute and UniFracImpute, identify and impute non-biological zeros in microbial count data by borrowing information from similar samples

What we need:

•	R 3.6.1 or later version

•	R packages: 
phyloseq, ape, phangorn, phytools, geiger,  scales, car

scDoc from https://github.com/anlingUA/scDoc/blob/master/scDoc_0.0.0.9.tar.gz

## Example code ##
## load phylogenetic tree and raw count data ##

phytree <- read.tree(file="phylotree.tre")

otu.tab <- read.csv("otu_example.csv",row.names = 1,check.names = FALSE)

####### Perform PhyImpute Imputation ##############

output1<-phyimpute(otudata=otu.tab, tree=phytree)

####### Perform UniFracImpute Imputation ###########

output2 <- unifracimpute(otudata=otu.tab, tree=phytree)

####### Plot the Results ##########

plot(output1, main="PhyImpute")
plot(output2, main="UniFracImpute")
