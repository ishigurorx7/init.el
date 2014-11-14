init.el
=======

GNU Emacs setup file for cscope feature.

Introduction
=========

init.el is well known initial setup file for GNU Emacs, and it should be located on the following location:

~/.emacs.d/init.el

The posted init.el was borrowed from following site, and added cscope feature:

http://www.cs.utah.edu/~aek/code/init.el.html

Following codes were added to enable cscope feature in original init.el:

;; Cscope                                                                                                              ;; ------                                                                                                              ;; Added cscope feature. Emacs need to load xcscope.el file                                                            ;; which is program to interface to the cscope feature, and we                                                         ;; assumes that the file is located on the following place:                                                            ;; "/usr/share/emacs/site-lisp/xcscope/xcscope.el"                                                                     ;;                                                                                                                          
(load-file "/usr/share/emacs/site-lisp/xcscope/xcscope.el")

(require 'xcscope)

(setq cscope-do-not-update-database t)

(add-hook 'asm-mode-hook (function cscope:hook))

Tested env
==========
The posted init.el was tested on the following environment:

* Ubuntu 14.0.4
* x86 64bits
* Linux 3.18.0-031800rc4-generic
* GNU Emacs 24.3.1
* cscope (version 15.8a)
* xscope-el (version 1.0-2)
 
References
==========
* Original init.el       http://www.cs.utah.edu/~aek/code/init.el.html
* xcscope.el  download   http://packages.ubuntu.com/trusty/devel/xcscope-el
* xcscope doc            http://www.emacswiki.org/emacs/CScopeAndEmacs#toc2  
* cscope command         http://linux.die.net/man/1/xcscope

