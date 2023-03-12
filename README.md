# RaceInjector-counterexamples

This repository contains counterexamples described in `RaceInjector: Injecting Races To Evaluate And Learn Dynamic Race Detection Algorithms` by Michael Wang, Shashank Srikant, Malavika Samak, Una-May O'Reilly, 2023.

Link to paper - [link]

Citation
```
@inproceedings{
	[citation]
}
```

The counterexamples, which are generated by our method `RaceInjector`, are program execution traces with a guaranteed race condition in them which recent race detection algorithms fail to detect.

For clarifications, please contact Michael (mi27950@mit.edu) or Shashank (shash@mit.edu).

## Folder structure

`treeset_orig`, `arraylist_orig`, and `jigsaw_orig` are the original _base traces_ collected by Calfuzzer.

These traces correspond to the following program benchmarks:
- TreeSet 
- ArrayList
- JigSaw 

The race detection algorithms evaluated are:
- **Happens-Before (HB; Lamport, 1976)** [[link]](https://lamport.azurewebsites.net/pubs/time-clocks.pdf)
- **Schedulable Happens-Before (SHB; Mathur _et al._, 2018)** [[link]](https://dl.acm.org/doi/abs/10.1145/3276515)
- **Weak Causally Precedes (WCP; Kini _et al._, 2017)** [[link]](https://arxiv.org/pdf/1704.02432.pdf)
- **SyncP (Mathur _et al._, 2021)** [[link]](https://dl.acm.org/doi/10.1145/3434317)


The folder `./{algorithm}_missed` contains counterexamples generated for each program benchmark corresponding to the algorithm.  
For example, `syncp_missed/treeset` contains all the traces generated from the `TreeSet` base trace that each contain a RaceInjector-injected race condition which `SyncP` fails to detect.
