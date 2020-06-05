# AnvioError_200605
Data relevant to Anvio errors during profiling


Files:

GenContDB.err.txt - stderr during anvi-gen-contigs-database using same contigs for read mapping

GenContDB.out.txt - stdout during anvi-gen-contigs-database using same contigs for read mapping

NOTTroublMap.err.txt - stderr of non-issue readset mapping to contigs (BBmap)

NOTTroublMap.out.txt - stdout of non-issue readset mapping to contigs (BBmap)

NOTTroublMap.ReadLeng.txt - histogram formatted read lengths of non-issue readset mapping to contigs (BBmap)

NOTTroublMap.InsertLeng.txt - histogram formatted insert lengths of non-issue readset mapping to contigs (BBmap)

NOTTroublMap.Stats.txt - mapping statistics of non-issue readset mapping to contigs (BBmap)

      Note, non-issue reads are not provided, and that theses reads were overall less deeply sequenced than the issue reads

TroublMap.err.txt - stderr of issue readset mapping to contigs (BBmap)

TroublMap.out.txt - stdout of issue readset mapping to contigs (BBmap)

TroublMap.ReadLeng.txt - histogram formatted read lengths of issue readset mapping to contigs (BBmap)

TroublMap.InsertLeng.txt - histogram formatted insert lengths of issue readset mapping to contigs (BBmap)

TroublMap.Stats.txt - mapping statistics of non-issue readset mapping to contigs (BBmap)

TroublMapProf_RUNLOG.txt - runlog generated during anvi-profile using issue reads

TroublMapProf.err.txt - stderr during anvi-profile of issue reads mapped to the fasta used to create the dontigs database

TroublMapProf.out.txt - stdout during anvi-profile of issue reads mapped to the fasta used to create the dontigs database

      Note, this profile attempt was forcibly cancelled after ~1 hour, but originally ran for ~23 hours until workload manager killed the job. Other profiles on similar sized reads sets mapped to the same contigs finished within minutes.


Error (deviation from completing anvi-profile runlogs):

[04 Jun 20 13:22:36 Profiling w/20 threads] 4770/30674 contigs :gear: | MEMORY :brain: 29.14 GB (+122.66 MB)     ETA: 2m20sProcess Process-3:
Traceback (most recent call last):
 File “/usr/local/bioinfo/Anaconda3/envs/anvio6/lib/python3.6/multiprocessing/process.py”, line 258, in _bootstrap
  self.run()
 File “/usr/local/bioinfo/Anaconda3/envs/anvio6/lib/python3.6/multiprocessing/process.py”, line 93, in run
  self._target(*self._args, **self._kwargs)
 File “/usr/local/bioinfo/Anaconda3/envs/anvio6/lib/python3.6/site-packages/anvio/profiler.py”, line 595, in profile_contig_worker
  contig = self.process_contig(bam_file, contig_name, contig_length)
 File “/usr/local/bioinfo/Anaconda3/envs/anvio6/lib/python3.6/site-packages/anvio/profiler.py”, line 659, in process_contig
  split.auxiliary.process(bam_file)
 File “/usr/local/bioinfo/Anaconda3/envs/anvio6/lib/python3.6/site-packages/anvio/contigops.py”, line 191, in process
  self.run_SNVs(bam)
 File “/usr/local/bioinfo/Anaconda3/envs/anvio6/lib/python3.6/site-packages/anvio/contigops.py”, line 414, in run_SNVs
  for read in bam.fetch_and_trim(self.split.parent, self.split.start, self.split.end):
 File “/usr/local/bioinfo/Anaconda3/envs/anvio6/lib/python3.6/site-packages/anvio/bamops.py”, line 83, in fetch_and_trim
  read.trim(trim_by=(read.reference_end - end), side=‘right’)
 File “/usr/local/bioinfo/Anaconda3/envs/anvio6/lib/python3.6/site-packages/anvio/bamops.py”, line 269, in trim
  ” range of %d” % (trim_by, self.reference_end - self.reference_start))
anvio.errors.ConfigError: 
Config Error: Read.trim :: Requesting to trim an amount 818 that exceeds the alignment range
       of 251                                     
[04 Jun 20 13:22:36 Profiling w/20 threads] 30673/30674 contigs :gear: | MEMORY :brain: 28.53 GB (+4.05 MB)       ETA: 0s
