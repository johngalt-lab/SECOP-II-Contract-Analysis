# SECOP-II-Contract-Analysis
This project uses the free data in datos.gov.co to spot unusual contracts by their characteristics using machine learning models. 

## Clean and Describe
Here I do a bit of cleaning up of the dataset and describe what I can see with some simple questions that help me understand better the dataset. This I did with a subsample of 5000 rows. 
- Are contract IDs unique in this extract? Yes. 
- How many values, dates, and added-day fields are missing? Some, mainly in "fecha_de_inicio_de_contrato" or start dates of the contracts. When I check deeper, I can see interesting stuff.
- The calculated durations seem correct? This came up from checking null values in the previous question. 
- Are there zero or negative contract values? Some 0 values that need to be further checked. 
- Do any end dates precede start dates? No. I think this might have to do with an input restriction, the careful input by the person inputting the contract dates or just normal behavior
- Which contract types and procurement methods dominate? This gets a different response for different attributes:
    - By department, Putumayo and La Guajira seem to have the biggest bubbles (3.48 and 1.93 Millions respectively).
    - By sector, the "TIC" are the ones dominating visibly with a bubble size of 30.96 Millions. 
    - By rama, "Legislativo" dominates with 6.24 Millions
    - By "estado_contrato" Suspended contracts and modified contracts dominate with 2.96 and 1.84 respectively
    - By "tipo_de_contrato" Obra, Suministros and Consultoria lead with 6.7, 4.6 and 4
    - By "modalidad_de_contratacion" Licitación pública and "Contratación con regimen especial" lead with 14 and 11 Millions
    - By "es_grupo" "Yes" wins by a lot 10.7 against 0.6 for "No"
- How many contracts have positive added days? About 49. Not sure what to do with this right now
- Are enough comparable contracts available within each group? Need to still check this. I am having groups for each attribution here:
    - By rama, "Ejecutivo" dominates with 4069 records
    - By "tipo_de_contrato" Prestación de servicios dominates with 4324 rows. 
    - By "modalidad_de_contratacion" "Contratación directa" has 4048 records while the others are very few
    - By "es_grupo" "No" wins by a lot 4958 against 42 for "Yes"
    - The gender here also impacts but now I understand why... groups don't have a gender when it comes to legal representative... I thought they did but it seems like they do not
