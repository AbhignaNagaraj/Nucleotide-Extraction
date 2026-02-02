🧬 FASTA Subsequence Extractor
A lightweight Python utility for extracting genomic subsequences from FASTA files using Biopython. Designed for fast, reproducible coordinate-based sequence retrieval from large genomes.


🚀 Quick Start
1️⃣ Install Dependencies
pip install biopython
2️⃣ Clone the Repository
git clone https://github.com/your-username/fasta-subsequence-extractor.git
cd fasta-subsequence-extractor
3️⃣ Run the Script
python extract_subsequence.py


📦 Requirements
Python ≥ 3.7
Biopython ≥ 1.78


📂 Input Parameters
Parameter	Description
fasta_file_path	Path to input FASTA file
start_pos	Start coordinate (0-based indexing)
end_pos	End coordinate (0-based indexing)



⚠️ Important
Biopython uses 0-based indexing. Convert coordinates accordingly if using 1-based genomic annotations.

🧪 Example Usage
from Bio import SeqIO

def extract_sequence_from_fasta(fasta_file_path, start_pos, end_pos):
    try:
        with open(fasta_file_path, 'r') as fasta_file:
            records = SeqIO.parse(fasta_file, 'fasta')
            for record in records:
                sequence = record.seq
                subsequence = sequence[start_pos:end_pos]
                print(
                    f"Subsequence ({start_pos}-{end_pos}):\n{subsequence}"
                )

    except FileNotFoundError:
        print("File not found:", fasta_file_path)
    except Exception as e:
        print("Error:", str(e))

fasta_file_path = '/content/Escherichia_coli_ATCC_11775.fasta'
start_pos = 1340073
end_pos = 1340972

extract_sequence_from_fasta(fasta_file_path, start_pos, end_pos)


📤 Output
The extracted subsequence is printed to STDOUT:
Subsequence (1340073-1340972):
ATGCGT...


Applications
Gene and operon extraction
Primer / antisense oligonucleotide design
Genome annotation validation
Comparative genomics pipelines


🔧 Roadmap
 Command-line interface (CLI)
 FASTA output support
 Strand selection (forward / reverse complement)
 Multi-region batch extraction


🤝 Contributing
Contributions are welcome!
Fork the repository
Create a feature branch
Commit your changes
Open a pull request


📜 License
MIT License — free for academic, research, and commercial use.

📫 Contact
Abhigna N U
Ph.D. in Bioinformatics
📧 abhignanagaraj95@gmail.com

⭐ If this tool helps your research, consider starring the repo!
