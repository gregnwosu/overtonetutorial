(ns tutorial.core
  (:require [overtone.core :refer :all]
            [overtone.inst.piano :refer :all]))

(defn play-chord [chord]
  (doseq [note chord] (piano note)))

(defn tune [] (let [time (now)]
                (at time (play-chord (chord :C3 :major7)))
                (at (+ 1000 time ) (play-chord (chord :C3 :major7)))
                (at (+ 2000 time ) (play-chord (chord :E3 :minor)))
                (at (+ 3000 time ) (play-chord (chord :A2 :minor)))
                ))

(defsynth bar [freq 440]
  (out 0 (sin-osc freq)))

(bar 500)
(kill bar)

(definst beep [note 60]
  (let [sound-src (sin-osc (midicps note))
        env (env-gen (perc 0.01 1.0) :action FREE)]
    (* sound-src env)))


(beep 60)

(defsynth pad1 [freq 110 amp 1 gate 1 out-bus 0]
  (out out-bus (* (saw [freq (* freq 1.01)])
                  (env-gen (adsr 0.01 0.1 0.7 0.5) :gate gate :action FREE))))

(pad1)
(stop)


(definst steel-drum [note 60 amp 0.8]
  (let [freq (midicps note)]
    (* amp
       (env-gen (perc 0.01 0.2) 1 1 0 1 :action FREE)
       (+ (sin-osc (/ freq 2))
          (rlpf (saw freq) (* 1.1 freq) 0.4)))))

(piano 60)

(def snare (sample (freesound-path 26903)))
