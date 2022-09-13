- 👋 Hi, I’m @PrigasG - George 
- 👀 I’m interested in data research and analysis
- 🌱 I have been working on R markdown and Quarto
- 💞️ I’m looking to collaborate on any fun projects/ R markdown/ Quarto/ Python
- 📫 How to reach me prigasgenthian48@gmail.com/ george8.arthur9@gmail.com
- twitter: @GenthianPrigas

<!---
PrigasG/PrigasG is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

Read different files in R studio

r.read.files <- function(type, file){
  if (type == "csv"){

    result <- read.csv(paste(file,".csv", sep = ""))
    #if (!vprint) print(result)
    header <- lapply(result, function(x) type.convert(x))
    #try using the janitor::row_to_names(result)
  } else if (type %in% c("xlsx", "xls")) {
    result <- readxl::read_excel(paste(file, ".xlsx", sep = ""))
    #if(!vprint) print(result)
  } else if (type == "rds"){
    result <- readRDS(paste(file, ".rds", sep = ""))
  } else if (type %in% c("sas7bdat", "sasbdat")){
    result <- haven::read_sas(paste(file, ".sas7bdat"))
  } else {
    print("no values")
  }
}
