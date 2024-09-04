## Simulation

Each experiment is defined by hydra configuration. To run an experiment, use 
`python3 -m simulation.main experiment=<scenario_name>_<experiment_name>`.
For example, to run the experiment `fish_baseline_concurrent` , use
`python3 -m simulation.main experiment=fish_baseline_concurrent`. See below for the list of experiments and their ids.

```
python3 -m simulation.main experiment=<experiment_id> llm.path=<path_to_llm>
```



### Table of experiments
| Experiment in the paper      | Fishery  | Pasture | Pollution | 
| ------------------------------------ |---------------- |-------------------- | -------------- |
| Default setting   |     fish_baseline_concurrent         |      sheep_baseline_concurrent       | pollution_baseline_concurrent |
| Introuducing universalization | fish_baseline_concurrent_universalization | sheep_baseline_concurrent_universalization | pollution_baseline_concurrent_universalization |
| Ablation: no language | fish_perturbation_no_language | sheep_perturbation_no_language | pollution_perturbation_no_language |
| Greedy newcomer | fish_perturbation_outsider | - | - |
| Asymmetry: family background | fish_family_bg_univ | - | - |


### Running mixed-llm experiments

- Use the following command: `python -m simulation.main experiment={experiment_name} -cn multi_config`
- Either use hydra CLI options to add more LLM paths for your mixed, or add them manually by editing the llm.path group in `multi_config.yaml` file under the `conf` directory.