# Create Patient Similarity Networks from Input Data

<a id="overview">
## Overview
Defining meaningful patient similarity networks (or features) is the key to building a high-performing classifier. It is also crucial to using netDx for clinical discovery. When designing patient similarity networks, two considerations are the level at which individual variables should be grouped, and the measure used to define patient similarity. 

## Grouping variables
In a given datatype, not all measured variables are equally predictive. Moreover some groupings of variables may be more informative about mechanism, perhaps because they use prior knowledge. Such variables are more interpretable, as they reflect some process of clinical or biological relevance. For each datatype, the user needs to decide which level of variable-grouping to apply. 

This table provides some examples for different types of data. Consider the lung cancer example from the [Introduction](Introduction), and assume we measure: 34 clinical variables; 20,000 genes; 16 metabolites; and genetic mutations from whole-genome sequencing.

<table cellspacing="0" border=1>
<tr>
	<th>Type of data</th>
	<th>1 variable per network</th>
	<th>All variable per network</th>
	<th>Subset of variables per network</th>
</tr>
<tr>
	<td style="spec">Clinical data</td>
	<td style="">Age or sex or smoking frequency <i>(34 networks)</i></td>
	<td style="">Clinical data <i>(1 network)</i></td>
	<td style="">a set of 5 variables measuring lung condition <i>(2-27 networks)</td>
</tr>
<tr>
	<td style="spec">Gene expression</td>
	<td style="">Top 10 known high-risk genes, one gene per network<i>(10 networks)</i></td>
	<td style="">All gene expression data<i>(1 network)</i></td>
	<td style="">Genes grouped by pathways <i>(~2,000 networks)</td>
</tr>
<tr>
	<td style="spec">Metabolic data</td>
	<td style="">3 metabolites identified through other statistical analyses<i>(3 networks)</i></td>
	<td style="">All metabolite data<i>(1 network)</i></td>
	<td style="">Metabolites grouped by biological process they affect <i>(3-4 networks)</td>
</tr>
<tr>
	<td style="spec">Genetic data</td>
	<td style="">Top genes from GWAS studies <i>(~10 networks)</i></td>
	<td style="">All genetic data<i>(1 network)</i></td>
	<td style="">Genes grouped by pathways <i>(~2,000 networks)</td>
</tr>
</table>


Patient similarity can be measured in different ways for different types of input data. The figure below provides a rough guideline to defining a similarity metric for a given set of vari 

<a id="summary"> </a>
## Summary table
<table cellspacing="0" border=1>
<tr> 
	<th>Type of data</th>
	<th>Example</th> 
	<th>Similarity measure</th>
	<th>Example call</th> 
</tr>
<tr> <th class="spec">Continous, over 5 vars </th>             
	<td class="">Gene expression</td>
	<td class="">Pearson correlation</th>
	<td class="code">makePSN_NamedMatrix(xpr,gene_names, 
				netDir,writeProfiles=TRUE)
</tr>
<tr> <th class="spec">Continous, over 5 vars </th>             
	<td class="">Gene expression</td>
	<td class="">Pearson correlation</th>
	<td class="code">makePSN_NamedMatrix(writeProfiles=TRUE)
</tr>
</table>

<a id="pearson"></a>
## Expression data

<a id="avg_normdiff"></a>
## Fewer than 5 datapoints 
average normalized difference

<a id="binary_nets"></a>
## Range-based data (genetic mutations)

<a id="howto_emap"></a>
## Setting up to get an enrichment map




