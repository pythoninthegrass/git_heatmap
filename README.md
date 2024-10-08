# git_heat_map

`ghm` (`git_heat_map`) is a simple CLI tool to show the most commonly changed files / directories in a git repo.

## Minimum Requirements

* macOS / Linux / WSL
* [git](https://git-scm.com/)
* [gum](https://github.com/charmbracelet/gum?tab=readme-ov-file#installation)

## Recommended Requirements

* [asdf](https://asdf-vm.com/)

## Installation

```bash
# clone repo
git clone https://github.com/pythoninthegrass/git_heatmap.git
cd git_heat_map
```

> [!NOTE]
> Symlink the script to a directory in your `$PATH` to run it from anywhere.

```bash
ln -s $(pwd)/git_heat_map.sh ~/.local/bin/ghm
```


## Quickstart

```bash
# run script as-is
λ ghm
  ▌ Git Heat Map Results
  
  Changes│File/Folder    
  ───────┼───────────────
  2      │git-heat-map   
  1      │git_heat_map.sh
  1      │README.md      
  1      │.tool-versions 

# run script with arguments
λ USE_GUM=true LOG=log ghm 5
  ▌ Git Heat Map Results
  
  Changes│File/Folder    
  ───────┼───────────────
  2      │git-heat-map   
  1      │git_heat_map.sh
  1      │README.md      
  1      │.tool-versions

λ USE_GUM=true LOG=both ghm 5
Wed, 02 Oct 2024 18:06:33 CDT INFO Git repository detected at ~/git/git_heatmap
Wed, 02 Oct 2024 18:06:33 CDT INFO Fetching git commit data for 5 results
Wed, 02 Oct 2024 18:06:33 CDT INFO Formatting output
  ▌ Git Heat Map Results
  
  Changes│File/Folder    
  ───────┼───────────────
  2      │git-heat-map   
  1      │git_heat_map.sh
  1      │README.md      
  1      │.tool-versions 
Wed, 02 Oct 2024 18:06:33 CDT INFO Git heat map generation complete

# check log file
λ cat /tmp/git_heat_map.log 
Wed, 02 Oct 2024 17:49:26 CDT INFO Git repository detected at ~/git/git_heatmap
Wed, 02 Oct 2024 17:49:26 CDT INFO Fetching git commit data for 5 results
Wed, 02 Oct 2024 17:49:26 CDT INFO Formatting output
Wed, 02 Oct 2024 17:49:26 CDT INFO Git heat map generation complete
```

## Environment Variables

| Variable   | Description                                              |
|------------|----------------------------------------------------------|
| `USE_GUM`  | Use gum for styling (default: true)                      |
| `LOG`      | Log to stdout, log file, both, or false (default: false) |
| `LOG_DIR`  | Directory to store log file (default: /tmp)              |
| `LOG_FILE` | Log file name (default: git_heat_map.log)                |
