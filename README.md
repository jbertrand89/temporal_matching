# README

## Saved test episodes

For more details on the datasets, please refer to [DATA_PREPARATION](https://github.com/jbertrand89/temporal_matching/blob/main/DATA_PREPARATION.md).

For reproducibility, we pre-saved the 10k test episodes for the datasets:
* Something-Something v2, the few-shot split
* Kinetics-100, the few-shot split
* UCF101, the few-shot split




You can download them using the following script.

```
ROOT_TEST_EPISODE_DIR=<your_path>

for DATASET in "ssv2"
do
    DATASET_TEST_EPISODE_DIR=${ROOT_TEST_EPISODE_DIR}/${DATASET}
    mkdir ${DATASET_TEST_EPISODE_DIR}
    DATASET_TEST_FEATURE_DIR=${DATASET_TEST_EPISODE_DIR}/features
    mkdir ${DATASET_TEST_FEATURE_DIR}
    cd ${DATASET_TEST_FEATURE_DIR}
    
    wget http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/data/test_examples/${DATASET}/features/${DATASET}_w5_s1.tar.gz
    tar -xzf ${DATASET}_w5_s1.tar.gz
    rm -r ${DATASET}_w5_s1.tar.gz
    
    wget http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/data/test_examples/${DATASET}/features/${DATASET}_w5_s5.tar.gz
    tar -xzf ${DATASET}_w5_s5.tar.gz
    rm -r ${DATASET}_w5_s5.tar.gz
done
```


The following table provides you the specifications of each dataset.
<table>
  <thead>
    <tr style="text-align: right;">
      <th>Dataset</th>
      <th>Backbone</th>
      <th>#shot</th>
      <th>#classes (way) </th>
      <th>Episode count</th>
      <th>Episodes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ssv2</th>
      <th>R2+1D</th>
      <th>1</th>
      <th>5</th>
      <th>10000</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/data/test_examples/ssv2/features/ssv2_w5_s1.tar.gz">ssv2_w5_s1</a></td>
    </tr>
    <tr>
      <th>ssv2</th>
      <th>R2+1D</th>
      <th>5</th>
      <th>5</th>
      <th>10000</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/data/test_examples/ssv2/features/ssv2_w5_s5.tar.gz">ssv2_w5_s5</a></td>
    </tr>
    <tr>
      <th>kinetics100</th>
      <th>R2+1D</th>
      <th>1</th>
      <th>5</th>
      <th>10000</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/data/test_examples/kinetics100/features/kinetics100_w5_s1.tar.gz">kinetics100_w5_s1</a></td>
    </tr>
    <tr>
      <th>kinetics100</th>
      <th>R2+1D</th>
      <th>5</th>
      <th>5</th>
      <th>10000</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/data/test_examples/kinetics100/features/kinetics100_w5_s5.tar.gz">kinetics100_w5_s5</a></td>
    </tr>
    <tr>
      <th>ucf101</th>
      <th>R2+1D</th>
      <th>1</th>
      <th>5</th>
      <th>10000</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/data/test_examples/ucf101/features/ucf101_w5_s1.tar.gz">ucf101_w5_s1</a></td>
    </tr>
    <tr>
      <th>ucf101</th>
      <th>R2+1D</th>
      <th>5</th>
      <th>5</th>
      <th>10000</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/data/test_examples/ucf101/features/ucf101_w5_s5.tar.gz">ucf101_w5_s5</a></td>
    </tr>

  </tbody>
</table>


## Inference


### Model zoo


<table>
  <thead>
    <tr style="text-align: right;">
      <th>Dataset</th>
      <th>Matching method</th>
      <th>Backbone</th>
      <th>Accuracy 1-shot</th>
      <th>Accuracy 5-shots</th>
      <th>Download models</th>
      <th>Inference from saved episodes</th>
      <th>Inference from dataloader</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ssv2</th>
      <th>mean</th>
      <th>R2+1D</th>
      <th>65.8 +- 0.0</th>
      <th>79.1 +- 0.1</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/mean/download_ssv2_mean_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/mean/inference_ssv2_mean_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/mean/inference_loader_ssv2_mean_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ssv2</th>
      <th>max</th>
      <th>R2+1D</th>
      <th>65.0 +- 0.2</th>
      <th>79.0 +- 0.0</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/max/download_ssv2_max_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/max/inference_ssv2_max_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/max/inference_loader_ssv2_max_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ssv2</th>
      <th>chamfer++</th>
      <th>R2+1D</th>
      <th>67.8 +- 0.2</th>
      <th>81.6 +- 0.1</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/chamfer++/download_ssv2_chamfer++_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/chamfer++/inference_ssv2_chamfer++_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/chamfer++/inference_loader_ssv2_chamfer++_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ssv2</th>
      <th>diagonal</th>
      <th>R2+1D</th>
      <th>66.7 +- 0.1</th>
      <th>80.1 +- 0.0</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/diag/download_ssv2_diag_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/diag/inference_ssv2_diag_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/diag/inference_loader_ssv2_diag_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ssv2</th>
      <th>linear</th>
      <th>R2+1D</th>
      <th>66.6 +- 0.1</th>
      <th>80.1 +- 0.2</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/linear/download_ssv2_linear_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/linear/inference_ssv2_linear_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/linear/inference_loader_ssv2_linear_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ssv2</th>
      <th>otam</th>
      <th>R2+1D</th>
      <th>67.1 +- 0.0</th>
      <th>80.2 +- 0.2</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/otam/download_ssv2_otam_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/otam/inference_ssv2_otam_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/otam/inference_loader_ssv2_otam_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ssv2</th>
      <th>trx</th>
      <th>R2+1D</th>
      <th>65.1 +- 0.2</th>
      <th>82.0 +- 0.0</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/trx/download_ssv2_trx_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/trx/inference_ssv2_trx_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/trx/inference_loader_ssv2_trx_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ssv2</th>
      <th>visil</th>
      <th>R2+1D</th>
      <th>67.7 +- 0.0</th>
      <th>81.3 +- 0.0</th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/visil/download_ssv2_visil_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/visil/inference_ssv2_visil_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ssv2/visil/inference_loader_ssv2_visil_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>kinetics100</th>
      <th>mean</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/mean/download_kinetics100_mean_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/mean/inference_kinetics100_mean_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/mean/inference_loader_kinetics100_mean_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>kinetics100</th>
      <th>max</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/max/download_kinetics100_max_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/max/inference_kinetics100_max_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/max/inference_loader_kinetics100_max_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>kinetics100</th>
      <th>chamfer++</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/chamfer++/download_kinetics100_chamfer++_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/chamfer++/inference_kinetics100_chamfer++_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/chamfer++/inference_loader_kinetics100_chamfer++_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>kinetics100</th>
      <th>diagonal</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/diag/download_kinetics100_diag_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/diag/inference_kinetics100_diag_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/diag/inference_loader_kinetics100_diag_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>kinetics100</th>
      <th>linear</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/linear/download_kinetics100_linear_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/linear/inference_kinetics100_linear_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/linear/inference_loader_kinetics100_linear_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>kinetics100</th>
      <th>otam</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/otam/download_kinetics100_otam_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/otam/inference_kinetics100_otam_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/otam/inference_loader_kinetics100_otam_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>kinetics100</th>
      <th>trx</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/trx/download_kinetics100_trx_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/trx/inference_kinetics100_trx_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/trx/inference_loader_kinetics100_trx_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>kinetics100</th>
      <th>visil</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/visil/download_kinetics100_visil_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/visil/inference_kinetics100_visil_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/kinetics100/visil/inference_loader_kinetics100_visil_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ucf101</th>
      <th>mean</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/mean/download_ucf101_mean_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/mean/inference_ucf101_mean_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/mean/inference_loader_ucf101_mean_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ucf101</th>
      <th>diagonal</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/diag/download_ucf101_diag_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/diag/inference_ucf101_diag_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/diag/inference_loader_ucf101_diag_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ucf101</th>
      <th>linear</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/linear/download_ucf101_linear_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/linear/inference_ucf101_linear_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/linear/inference_loader_ucf101_linear_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ucf101</th>
      <th>otam</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/otam/download_ucf101_otam_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/otam/inference_ucf101_otam_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/otam/inference_loader_ucf101_otam_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
    <tr>
      <th>ucf101</th>
      <th>trx</th>
      <th>R2+1D</th>
      <th></th>
      <th></th>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/trx/download_ucf101_trx_5way_all_shots_all_seeds.txt">script_download</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/trx/inference_ucf101_trx_5way_1shots_all_seeds.txt">script_inference</a></td>
      <td><a href="http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/ucf101/trx/inference_loader_ucf101_trx_5way_1shots_all_seeds.txt">script_from_loader</a></td>
    </tr>
  </tbody>
</table>

### Run inference for a pretrained model on the saved episodes

You need to
* download the pretrained models for multiple seeds (the script does it simultaneously for 1 shot and 5 shots)
* run the inference script either for 1 shot or 5 shots

To illustrate the process, you can find below an example using the chamfer++ matching function:

#### Download the pretrained models
```
CHECKPOINT_DIR=<your_checkpoint_dir>
MATCHING_NAME=chamfer++
DATASET=ssv2
cd ${CHECKPOINT_DIR}
for SHOT in 1 5
do
    for SEED in 1 5 10
    do
      wget http://ptak.felk.cvut.cz/personal/bertrjul/temporal_matching/models/${DATASET}/${MATCHING_NAME}/${DATASET}_${MATCHING_NAME}_5way_${SHOT}shots_seed${SEED}.pt
    done
done
```

#### Inference

```
ROOT_TEST_EPISODE_DIR=<your_path>
CHECKPOINT_DIR=<your_checkpoint_dir>
ROOT_REPO_DIR=<your_repo_dir>
MATCHING_NAME=chamfer++
SHOT=1
DATASET=ssv2

TEMPORAL_MATCHING_REPO_DIR=${ROOT_REPO_DIR}/temporal_matching
cd ${TEMPORAL_MATCHING_REPO_DIR}
source ENV/bin/activate

for SEED in 1 5 10
do
  MODEL_NAME=${DATASET}_${MATCHING_NAME}_5way_${SHOT}shots_seed${SEED}.pt
  
  python run_matching.py \
  --num_gpus 1 \
  --num_workers 1 \
  --backbone r2+1d_fc \
  --feature_projection_dimension 1152 \
  --method matching-based \
  --matching_function chamfer \
  --video_to_class_matching joint \
  --clip_tuple_length 3 \
  --shot ${SHOT} \
  --way 5 \
  -c ${CHECKPOINT_DIR} \
  -r -m ${MODEL_NAME} \
  --load_test_episodes \
  --test_episode_dir ${ROOT_TEST_EPISODE_DIR} \
  --dataset_name ${DATASET}
done

python average_multi_seeds.py --result_dir ${CHECKPOINT_DIR} --result_template ${DATASET}_${MATCHING_NAME}_5way_${SHOT}shots_seed --seeds 1 5 10
```

### Run inference for a pretrained model on new episodes 



<pre>
ROOT_FEATURE_DIR=<your_path>
CHECKPOINT_DIR=<your_checkpoint_dir>
ROOT_REPO_DIR=<your_repo_dir>
MATCHING_NAME=chamfer++
SHOT=1
DATASET=ssv2
TEST_SEED=1
TEST_DIR=${ROOT_FEATURE_DIR}/${DATASET}/test

TEMPORAL_MATCHING_REPO_DIR=${ROOT_REPO_DIR}/temporal_matching
cd ${TEMPORAL_MATCHING_REPO_DIR}
source ENV/bin/activate

for SEED in 1 5 10
do
  MODEL_NAME=${DATASET}_${MATCHING_NAME}_5way_${SHOT}shots_seed${SEED}.pt
  
  python run_matching.py \
  --num_gpus 1 \ 
  --num_workers 1 \
  --backbone r2+1d_fc \
  --feature_projection_dimension 1152 \
  --method matching-based \
  --matching_function chamfer \
  --video_to_class_matching joint \
  --clip_tuple_length 3 \
  --shot ${SHOT} \
  --way 5  \
  -c ${CHECKPOINT_DIR} \
  -r -m ${MODEL_NAME}\
  <b>--split_dirs  ${TEST_DIR}</b> \
  <b>--split_names test </b> \
  <b>--split_seeds ${TEST_SEED}</b> \
  --dataset_name ${DATASET}
done

python average_multi_seeds.py --result_dir ${CHECKPOINT_DIR} --result_template ${DATASET}_${MATCHING_NAME}_5way_${SHOT}shots_seed --seeds 1 5 10
</pre>

## Training the models




