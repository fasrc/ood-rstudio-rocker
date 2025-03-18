# ood-rstudio-rocker
Open OnDemand RStudio Server app

## FASRC Cannon 

If you are running this app on FASRC's Cannon cluster, you can
simply clone to `~/.fasrcood/dev` and it will show in your [Sandbox
Apps](https://rcood.rc.fas.harvard.edu/pun/sys/dashboard/admin/dev/products). 

## Site-specific modifications

If you wish to use this app in a different cluster, some files need to edited to
conform to your site's OOD implementation. All necessary and potential
modifications are commented with a `site-specific` tag. For example, the file
`form.yml` has for slurm partition:

```
  bc_queue:
# site-specific: change default partition
    value: "shared"
```

List of files to edit:

1. [`form.yml`](form.yml)
2. [`manifest.yml`](manifest.yml)
3. [`template/before.sh.erb`](template/before.sh.erb)
4. [`template/script.sh.erb`](template/script.sh.erb)

This app assumes the cluster uses slurm as the scheduler. If you use a different
scheduler, you wil likely need to modify other files.

## Singularity containers

You can build the Singularity containers using the Singularity definition files
provided in this repository:

- [RELEASE 3.19](Singularity/release_3_19.def)
- [RELEASE 3.18](Singularity/release_3_18.def)
  
