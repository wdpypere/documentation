
### Types

 - `/software/symlink/structure_symlink_replace_option_entry`
    - `/software/symlink/structure_symlink_replace_option_entry/all`
        - Optional
        - Type: string
    - `/software/symlink/structure_symlink_replace_option_entry/dir`
        - Optional
        - Type: string
    - `/software/symlink/structure_symlink_replace_option_entry/dirempty`
        - Optional
        - Type: string
    - `/software/symlink/structure_symlink_replace_option_entry/file`
        - Optional
        - Type: string
    - `/software/symlink/structure_symlink_replace_option_entry/link`
        - Optional
        - Type: string
    - `/software/symlink/structure_symlink_replace_option_entry/none`
        - Optional
        - Type: string
 - `/software/symlink/structure_symlink_entry`
    - `/software/symlink/structure_symlink_entry/name`
        - Optional
        - Type: string
    - `/software/symlink/structure_symlink_entry/target`
        - Optional
        - Type: string
    - `/software/symlink/structure_symlink_entry/exists`
        - Optional
        - Type: boolean
    - `/software/symlink/structure_symlink_entry/delete`
        - Optional
        - Type: boolean
    - `/software/symlink/structure_symlink_entry/replace`
        - Optional
        - Type: structure_symlink_replace_option_entry
 - `/software/symlink/structure_symlink_context_entry`
    - `/software/symlink/structure_symlink_context_entry/name`
        - Optional
        - Type: string
    - `/software/symlink/structure_symlink_context_entry/value`
        - Optional
        - Type: string
 - `/software/symlink/structure_symlink_option_entry`
    - `/software/symlink/structure_symlink_option_entry/exists`
        - Optional
        - Type: boolean
    - `/software/symlink/structure_symlink_option_entry/replace`
        - Optional
        - Type: structure_symlink_replace_option_entry
 - `/software/symlink/component_symlink`
    - `/software/symlink/component_symlink/links`
        - Optional
        - Type: structure_symlink_entry
    - `/software/symlink/component_symlink/context`
        - Optional
        - Type: structure_symlink_context_entry
    - `/software/symlink/component_symlink/options`
        - Optional
        - Type: structure_symlink_option_entry
