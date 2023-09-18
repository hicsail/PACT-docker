# Running PACT & VisualPACT from Docker Hub

To use the provided `docker-compose.yml` file to run the PACT and VisualPACT containers, follow these steps:

1. Install Docker:
   Ensure you have Docker and Docker Compose installed on your system. If you haven't installed them yet, please refer to the official Docker documentation for installation instructions:

   - Docker: https://docs.docker.com/get-docker/

2. Complete post-installation steps for linux based systems :
   See instructions here https://docs.docker.com/engine/install/linux-postinstall/. Particulary, make sure to add your user to docker group to avoid permission issues on ubuntu. Do so by running,

   ```
   sudo usermod -aG docker $USER
   ```

3. Prepare Your Data Files:
   Make sure you have the required input files for PACT and VisualPACT in the following directories:

   - For PACT, the following example input files have been provided:

     - `./Intel/Intel_ID1_lcf.csv`
     - `./Intel/Intel.config`
     - `./Intel/modelParams_Intel.config`
     - `./Intel/Intel.grid.steady`

   - For VisualPACT, the following example files have been provided:
     - `/VisualPACT/Example_transient_data_files/IBMPower9transientheatsink_128x128.grid.cir.csv`
     - `/VisualPACT/Example_overlay_images/IBMPower9.png` (if you are using this command)

4. Adjust Paths :
   If you need to change the paths to your OWN input files or directories, make sure to modify the corresponding volume mappings in the `docker-compose.yml` file.

5. Set required environment variables.
   Execute setenv.sh by running

   ```
   source setenv.sh
   ```

6. Run the Containers:
   Open your terminal or command prompt, navigate to the directory containing your `docker-compose.yml` file, and run the following commands:

   To run PACT:

   ```
   docker-compose up pact_container
   ```

   Then Visual PACT:

   ```
   docker-compose up visual_pact_container
   ```

   This will start the PACT and VisualPACT containers as defined in the `docker-compose.yml` file.
   The output of the simulations will appear in the terminal once it is done running

Please note that the provided `docker-compose.yml` file assumes that the required input files for PACT and VisualPACT are correctly placed in the specified directories. Make sure your data files are in the right locations before running the containers.

If you would like to run the docker file by cloning the entire PACT repo, follow this link for directions. https://github.com/peaclab/PACT
