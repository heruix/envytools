.. _pdaemon:

======================================
PDAEMON: card management microprocesor
======================================

Contents:

.. toctree::
   :titlesonly:

   falcon
   io
   perf
   subintr
   user
   host
   mutex
   crc
   timer
   chsw
   iredir
   therm
   counter
   mmio
   epwr
   signal


Introduction
============

PDAEMON is a falcon-based engine introduced on GT215. Its main purpose is
autonomous power and thermal management, but it can be used to oversee any part
of GPU operation. The PDAEMON has many dedicated connections to various parts
of the GPU.

The PDAEMON is made of:

- :ref:`a falcon microprocessor core <pdaemon-falcon>`
- :ref:`standard falcon memory interface unit <falcon-memif>`
- :ref:`a simple channel load interface, replacing the usual PFIFO interface <pdaemon-chsw>`
- :ref:`various means of communication betwen falcon and host <pdaemon-host>`
- :ref:`engine power gating controllers for the PFIFO-connected engines <pdaemon-epwr>`
- :ref:`"idle" signals from various engines and associated idle counters <pdaemon-counter>`
- :ref:`misc simple input/output signals to various engines, with interrupt capability <pdaemon-signal>`
- :ref:`a oneshot/periodic timer, using daemon clock or PTIMER as clock source <pdaemon-timer>`
- :ref:`PMC interrupt redirection circuitry <pdaemon-iredir>`
- :ref:`indirect MMIO access circuitry <pdaemon-mmio>`
- :ref:`direct interface to all PTHERM registers <pdaemon-therm>`
- :ref:`CRC computation hardware <pdaemon-crc>`

.. todo:: and unknown stuff.

There are 5 revisions of PDAEMON:

- v0: GT215:MCP89 - the original revision
- v1: MCP89:GF100 - added a third instance of power gating controller for PVCOMP
  engine
- v2: GF100:GF119 - removed PVCOMP support, added second set of input/output
  signals and ???
- v3: GF119:GK104 - changed I[] space layout, added ???
- v4: GK104- - a new version of engine power gating controller and ???

.. todo:: figure out additions

.. todo:: this file deals mostly with GT215 version now
