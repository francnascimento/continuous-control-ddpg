# Continuous Control Using DDPG

![](./images/cc_20_.gif)



## Setup

To set up your python environment to run the code in this repository, follow the instructions below.

1. **Create (and activate) a new environment with Python 3.6.**

   - __Linux__ or __Mac__: 

   ```bash
   conda create --name cc-ddpg python=3.6
   source activate cc-ddpg
   ```

   - __Windows__: 

   ```bash
   conda create --name cc-ddpg python=3.6 
   activate cc-ddpg
   ```

2. **Clone the repository, and navigate to the `python/` folder.  Then, install several dependencies.**

```bash
git clone https://github.com/cj-mills/continuous-control-ddpg.git
cd continuous-control-ddpg/python
pip install .
```

3. **Download and unzip the Unity Environment.**

   - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
   - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
   - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
   - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)

4. **Move the Unity Environment to the  `env/` folder**

   ```bash
   ./continuous-control-ddpg/env/
   ```

5. **Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the `cc-ddpg` environment.**

```bash
python -m ipykernel install --user --name cc-ddpg --display-name "cc-ddpg"
```



## Environment Details

|                       Structure                        |                             Goal                             |
| :----------------------------------------------------: | :----------------------------------------------------------: |
| Double-jointed arm which can move to target locations. | The agents must move their hands to the goal location, and keep them there. |

| Number of Agents | State Size | Agent Action Size | Action Type | Action Value Range |
| :--------------: | :--------: | :---------------: | :---------: | :----------------: |
|        20        |     33     |         4         | Continuous  |      [-1, 1]       |

|                       Reward Function                        |                      Solve Requirements                      |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| +0.1 for each step that the agent's hand is in the goal location | average score of +30 over 100 consecutive episodes across all agents |



## Usage

1. **Activate the Environment:** run the command `source activate cc-ddpg`

2. **Launch the Notebook Server:** run the command `jupyter notebook`

3. **Set Kernel for Notebook:** Before running code in a notebook, change the kernel to match the `cc-ddpg` environment by using the drop-down `Kernel` menu.

4. 

### Train Agents

| Hyper-Parameters  | Description                                           |  Default   |
| ----------------- | ----------------------------------------------------- | :--------: |
| `random_seed`     | The random seed                                       |    `10`    |
| `lr_actor`        | Learning rate for the Actor Model                     |   `1e-4`   |
| `lr_critic`       | Learning rate for the Critic Model                    |   `3e-4`   |
| `w_decay`         | L2 weight decay for Critic Model                      |   `1e-5`   |
| `noise`           |                                                       |    `2`     |
| `theta`           |                                                       |   `0.15`   |
| `sigma`           |                                                       |   `0.2`    |
| `noise_reduction` |                                                       |  `0.9999`  |
| `buffer_size`     | The replay memory buffer size                         | `int(1e6)` |
| `batch_size`      | Mini-batch size                                       |   `256`    |
| `gamma`           | Reward discount factor                                |   `0.99`   |
| `tau`             | For soft update of target parameters                  |   `1e-3`   |
| `add_noise`       | Add noise to action space during training             |   `True`   |
| `update_every`    | Time step interval for learning from experiences      |    `4`     |
| `target_avg`      | Average score required to consider environment solved |   `30.0`   |
| `n_episodes`      | Maximum number of episodes to train the models        |   `2000`   |



### Examples

| Test Bed         |                                  |
| ---------------- | -------------------------------- |
| Operating System | Ubuntu 18.04.1 LTS 64-bit        |
| Processor        | i7-6700K                         |
| Memory           | 16 GB                            |
| Graphics         | GTX 1070 (NVIDIA Driver: 396.54) |

| Hyper-Parameters | Episodes to Solve |   Training Time    |
| ---------------- | :---------------: | :----------------: |
| All Default      |        360        | 1 hour 30 min 19 s |
